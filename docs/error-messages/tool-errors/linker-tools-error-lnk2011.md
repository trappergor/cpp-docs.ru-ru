---
title: Ошибка средств компоновщика LNK2011 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18562a21886508ff0766641f95ac2e15b76fd424
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095395"
---
# <a name="linker-tools-error-lnk2011"></a>Ошибка средств компоновщика LNK2011

предкомпилированный объект не связан. образ нельзя запустить

При использовании предкомпилированных заголовков, что все файлы объектов, созданных с помощью предварительно скомпилированных заголовков должны быть связаны в необходима LINK. Если у вас есть файл с исходным, используемом для создания предкомпилированного заголовка для использования с другими исходными файлами, теперь необходимо включить объектный файл, созданный вместе с предкомпилированного заголовка.

Например если скомпилировать файл с именем STUB.cpp для создания предкомпилированного заголовка для использования с другими исходными файлами, должно быть скомпоновано с STUB.obj или вы получите эту ошибку. В следующие командные строки строка используется для создания предкомпилированного заголовка, COMMON.pch, который используется с PROG1.cpp и PROG2.cpp в строках, 2 и 3. Файл STUB.cpp содержит только `#include` строк (же `#include` строк как PROG1.cpp и PROG2.cpp) и используется только для создания предкомпилированных заголовков. В последней строке STUB.obj должен быть скомпонован в избежание LNK2011.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```