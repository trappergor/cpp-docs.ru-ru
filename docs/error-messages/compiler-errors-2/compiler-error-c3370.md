---
title: Ошибка компилятора C3370 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3370
dev_langs:
- C++
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dfd3ed72e379af754af53422842f88911916a79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135819"
---
# <a name="compiler-error-c3370"></a>Ошибка компилятора C3370

"имя_модуля_idl": idl_module еще не определен

Прежде чем использовать [idl_module](../../windows/idl-module.md) для указания точки входа в DLL, вы должны сначала с помощью `idl_module` указать имя библиотеки DLL.

В следующем примере возникает ошибка C3370:

```
// C3370.cpp
[module(name=MyLibrary)];
// uncomment the following line to resolve the error
// [idl_module(name="name1", dllname=x.dll)];
[idl_module(name="name1"), entry(100)] // C3370
int f1();

int main()
{
}
```