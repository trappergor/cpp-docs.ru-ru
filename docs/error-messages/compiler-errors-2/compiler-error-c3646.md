---
title: Ошибка компилятора C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 04ff1d026c97c56611f8b786d8a7254db711e4a8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769040"
---
# <a name="compiler-error-c3646"></a>Ошибка компилятора C3646

> «спецификатор»: Неизвестный спецификатор переопределения

## <a name="remarks"></a>Примечания

Компилятор обнаружил маркер в положение ожидал найти спецификатор переопределения, когда токен не был распознан компилятором.

Например если нераспознанный *описатель* — **_NOEXCEPT**, замените ключевое слово **noexcept**.

Дополнительные сведения см. в разделе [спецификаторы переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3646 и показывает способ ее устранения:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```