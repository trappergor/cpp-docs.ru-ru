---
title: Ошибка средств компоновщика LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 49fa7e7963d6bb561e1602b58fe1f26c5f3d54bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160475"
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