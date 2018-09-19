---
title: Ошибка средств компоновщика LNK1312 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 335a3976675f36e3da295bc23c8e17440a56a505
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088657"
---
# <a name="linker-tools-error-lnk1312"></a>Ошибка средств компоновщика LNK1312

Недопустимый или поврежденный файл: не удается импортировать сборку

При построении сборки в файл, модуля или сборки, скомпилированной с **/CLR** передан **добавившей** параметр компоновщика.  При передаче в объектный файл для **добавившей**, просто передайте объект непосредственно компоновщику, а не к **добавившей**.

## <a name="example"></a>Пример

Следующий пример создан OBJ-файле.

```
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1312.

```
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```