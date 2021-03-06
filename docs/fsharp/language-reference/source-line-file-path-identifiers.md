---
title: Identificadores de linha, arquivo e demarcador de origem (F#)
description: 'Saiba como usar o F # identificador valores internos que permitem que você acesse o número de linha de origem, o diretório e o nome do arquivo no seu código.'
ms.date: 05/16/2016
ms.openlocfilehash: 76b705fec0d951b12655edbe69e7c9212f50779d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565211"
---
# <a name="source-line-file-and-path-identifiers"></a>Identificadores de linha, arquivo e demarcador de origem

Os identificadores de `__LINE__`, `__SOURCE_DIRECTORY__` e `__SOURCE_FILE__` são valores internos que permitem acessar o nome de arquivo e diretório, número da linha de código-fonte em seu código.


## <a name="syntax"></a>Sintaxe

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Comentários
Cada um desses valores tem tipo `string`.

A tabela a seguir resume os identificadores de caminho que estão disponíveis no F #, de arquivo e a linha de origem. Esses identificadores não são macros de pré-processador; eles são valores internos que são reconhecidos pelo compilador.

|Identificador predefinida|Descrição|
|---------------------|-----------|
|`__LINE__`|Retorna o número da linha atual, considerando `#line` diretivas.|
|`__SOURCE_DIRECTORY__`|Avalia o caminho completo atual do diretório de origem, considerando `#line` diretivas.|
|`__SOURCE_FILE__`|É avaliada como o nome de arquivo de origem atual e seu caminho, considerando `#line` diretivas.|
Para obter mais informações sobre o `#line` diretiva, consulte [diretivas de compilador](compiler-directives.md).

## <a name="example"></a>Exemplo

O exemplo de código a seguir demonstra o uso desses valores.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Saída:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>Consulte também
[Diretivas de Compilador](compiler-directives.md)

[Referência da Linguagem F#](index.md)
