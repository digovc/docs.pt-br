---
title: Notificações de consulta no SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 60ab686437f764a006fca5a2043d02288ea46d0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364065"
---
# <a name="query-notifications-in-sql-server"></a>Notificações de consulta no SQL Server
Criado utilizando a infraestrutura de Service Broker, as notificações de consulta permitem que os aplicativos sejam notificados quando os dados tiverem sido alterados. Esse recurso é especialmente útil para aplicativos que fornecem um cache de informações de um banco de dados, como um aplicativo Web, e precisam ser notificados quando os dados de origem são alterados.  
  
 Há três maneiras de implementar as notificações de consulta usando ADO.NET:  
  
1.  A implementação de baixo nível é fornecida pela classe `SqlNotificationRequest` que expõe a funcionalidade do lado do servidor, permitindo que você execute um comando com uma solicitação de notificação.  
  
2.  A implementação de alto nível é fornecida pela classe `SqlDependency`, que é uma classe que fornece uma abstração de alto nível da funcionalidade de notificação entre o aplicativo de origem e o SQL Server, permitindo que você use uma dependência para detectar alterações no servidor. Na maioria dos casos, esse é o modo mais simples e mais eficiente de aproveitar o recurso de notificações do SQL Server por aplicativos cliente gerenciados usando o provedor de dados .NET Framework para SQL Server.  
  
3.  Além disso, os aplicativos Web criados usando o ASP.NET 2.0 ou posterior podem usar as classes auxiliares `SqlCacheDependency`.  
  
 As notificações de consulta são usadas para aplicativos que precisam atualizar exibições ou caches em resposta a alterações nos dados subjacentes. O Microsoft SQL Server permite que aplicativos do .NET Framework enviem um comando ao SQL Server e solicitem a notificação se executar o mesmo comando produzir conjuntos de resultados diferentes dos recuperados inicialmente. As notificações geradas no servidor são enviados por filas a serem processadas posteriormente.  
  
 Você pode configurar notificações para as instruções SELECT e EXECUTE. Ao usar uma instrução EXECUTE, o SQL Server registra uma notificação para o comando executado em vez da própria instrução EXECUTE. O comando deve atender aos requisitos e limitações para uma instrução SELECT. Quando um comando que registra uma notificação contém mais de uma declaração, o Mecanismo de Banco de Dados cria uma notificação para cada instrução no lote.  
  
 Se você estiver desenvolvendo um aplicativo em que você precisa notificações de subsegundos confiável quando dados são alterados, examine as seções **Planejando uma estratégia de notificações de consulta eficiente** e **alternativas para notificações de consulta** no [planejando notificações](http://go.microsoft.com/fwlink/?LinkId=211984) tópico nos Manuais Online do SQL Server. Para obter mais informações sobre as notificações de consulta e o SQL Server Service Broker, consulte os seguintes links para tópicos nos Manuais Online do SQL Server.  
  
 **SQL Server Books Online** (Guias online do SQL Server)  
  
-   [Usando notificações de consulta](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [Criando uma consulta para notificação](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [O Service Broker](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [InfoCenter do desenvolvedor do Service Broker](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [Desenvolvimento (Service Broker)](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a>Nesta seção  
 [Habilitando notificações de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 Descreve como usar as notificações de consulta, incluindo os requisitos para habilitá-las e usá-las.  
  
 [SqlDependency em um aplicativo ASP.NET](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 Demonstra como usar as notificações de consulta de um aplicativo ASP.NET.  
  
 [Detectando alterações com SqlDependency](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 Demonstra como detectar quando os resultados da consulta serão diferentes dos recebidos originalmente.  
  
 [Execução de SqlCommand com um SqlNotificationRequest](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Demonstra a configuração de um objeto <xref:System.Data.SqlClient.SqlCommand> para trabalhar com uma notificação de consulta.  
  
## <a name="reference"></a>Referência  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Descreve a classe <xref:System.Data.Sql.SqlNotificationRequest> e todos os seus membros.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Descreve a classe <xref:System.Data.SqlClient.SqlDependency> e todos os seus membros.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Descreve a classe <xref:System.Web.Caching.SqlCacheDependency> e todos os seus membros.  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server and ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md) (SQL Server e ADO.NET)  
 [ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
