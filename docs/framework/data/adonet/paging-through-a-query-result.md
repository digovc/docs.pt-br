---
title: "Paginação por meio de um resultado de consulta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b4a51eec840b74d04aaab97226191b2ed30d8826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="b2fb6-102">Paginação por meio de um resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="b2fb6-102">Paging Through a Query Result</span></span>
<span data-ttu-id="b2fb6-103">Paginação por meio de um resultado de consulta é o processo de retornar os resultados de uma consulta em subconjuntos menores de dados ou páginas.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="b2fb6-104">Essa é uma prática comum para exibir os resultados para um usuário em partes pequenas, fácil de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="b2fb6-105">O **DataAdapter** fornece um recurso para retornar apenas uma página de dados, por meio de sobrecargas do **preencher** método.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="b2fb6-106">No entanto, isso pode não ser a melhor escolha para paginação resultados de consultas grandes porque, embora o **DataAdapter** preenche o destino <xref:System.Data.DataTable> ou <xref:System.Data.DataSet> com apenas os registros solicitados, os recursos para retornar o toda consulta ainda são usados.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="b2fb6-107">Para retornar uma página de dados de uma fonte de dados sem o uso de recursos para retornar a consulta inteira, especifica critérios adicionais para a consulta que reduzem as linhas retornadas a apenas aqueles necessários.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="b2fb6-108">Para usar o **preencher** método para retornar uma página de dados, especifique um **startRecord** parâmetro para o primeiro registro na página de dados e um **maxRecords** parâmetro para o número de registros na página de dados.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="b2fb6-109">O exemplo de código a seguir mostra como usar o **preencher** método para retornar a primeira página de um resultado de consulta em que o tamanho da página é cinco registros.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="b2fb6-110">No exemplo anterior, o **DataSet** só é preenchida com cinco registros, mas toda a **pedidos** tabela é retornada.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="b2fb6-111">Para preencher o **DataSet** com os mesmos registros de cinco, mas somente retorno cinco registros, usar a parte superior e cláusulas WHERE na instrução SQL, como no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 <span data-ttu-id="b2fb6-112">Observe que, quando a paginação pelos resultados da consulta, dessa forma, você deve preservar o identificador exclusivo que ordena as linhas, para passar a ID exclusiva para o comando para retornar a próxima página de registros, conforme mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="b2fb6-113">Para retornar a próxima página de registros usando a sobrecarga do **preencher** método que utiliza o **startRecord** e **maxRecords** parâmetros, incrementar o índice atual do registro pelo o tamanho da página e o preenchimento de tabela.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="b2fb6-114">Lembre-se de que o servidor de banco de dados retorna os resultados de consulta inteira, embora apenas uma página de registros é adicionada para o **conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="b2fb6-115">No exemplo de código a seguir, as linhas da tabela são limpos antes que eles são preenchidos com a próxima página de dados.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="b2fb6-116">Deseja preservar um determinado número de linhas retornadas em um cache local para reduzir viagens ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="b2fb6-117">Para retornar a próxima página de registros sem ter que o servidor de banco de dados retornar a consulta inteira, especifique critérios restritivos a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="b2fb6-118">Como o exemplo anterior preservadas o último registro retornado, você pode usá-lo na cláusula WHERE para especificar um ponto de partida para a consulta, conforme mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2fb6-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2fb6-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b2fb6-119">See Also</span></span>  
 [<span data-ttu-id="b2fb6-120">DataAdapters e DataReaders</span><span class="sxs-lookup"><span data-stu-id="b2fb6-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="b2fb6-121">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b2fb6-121">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>