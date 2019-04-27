---
title: Ошибка компилятора C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: 33860273db07894a9a4d15ba6d578598a18819ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208061"
---
# <a name="compiler-error-c3836"></a>Ошибка компилятора C3836

статический конструктор не должна содержать список инициализации членов

Управляемый класс не может иметь статический конструктор, который также содержит список инициализации членов. Статические конструкторы классов вызываются среда CLR для инициализации статические данные-члены класса.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3836:

```
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
