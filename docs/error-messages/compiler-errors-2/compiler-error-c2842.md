---
title: Ошибка компилятора C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 99b2c86d1e914c9425c2664d4e858bba6cb99486
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325578"
---
# <a name="compiler-error-c2842"></a>Ошибка компилятора C2842

> "*класс*": управляемый или тип WinRT не может определять свой собственный «operator new» или «operator delete»

## <a name="remarks"></a>Примечания

Можно определить собственные **оператор new** или **оператор delete** для управления выделением памяти в неуправляемой куче. Однако эти операторы не могут быть определены в ссылочных классах , так как только они выделяются в управляемой куче.

Дополнительные сведения см. в разделе [определяемые пользователем операторы (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2842:

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
