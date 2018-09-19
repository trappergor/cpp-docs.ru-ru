---
title: Неустранимая ошибка C1197 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58561e7bd906fc750779ef53a4f68ec27088a3b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024766"
---
# <a name="fatal-error-c1197"></a>Неустранимая ошибка C1197

не может ссылаться на «mscorlib.dll_1», так как программой был уже адресован «mscorlib.dll_2»

Компилятор соответствует версии среды CLR.  Однако была предпринята попытка сослаться на версию файле среды CLR из предыдущей версии.

Чтобы устранить эту ошибку, только ссылки на файлы из версии общеязыковой среды выполнения, которая поставлялась с версией при компиляции с помощью Visual C++.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C1197:

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```