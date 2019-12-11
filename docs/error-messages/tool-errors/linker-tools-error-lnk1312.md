---
title: Ошибка средств компоновщика LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: e462d24f2eb54718ba73617146aab96bb14a66df
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990906"
---
# <a name="linker-tools-error-lnk1312"></a>Ошибка средств компоновщика LNK1312

Недопустимый или поврежденный файл: не удалось импортировать сборку

При построении сборки файл, отличный от модуля или сборки, скомпилированного с **параметром/CLR** , был передан параметру компоновщика **/ASSEMBLYMODULE** .  Если объектный файл был передан в **/ASSEMBLYMODULE**, просто передайте объект непосредственно в компоновщик, а не в **/ASSEMBLYMODULE**.

## <a name="example"></a>Пример

В следующем примере создается OBJ-файл.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1312.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
