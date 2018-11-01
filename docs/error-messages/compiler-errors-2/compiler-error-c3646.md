---
title: Ошибка компилятора C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: df2e52631ed75cc4a473429ea35e136ed0a88f98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606730"
---
# <a name="compiler-error-c3646"></a>Ошибка компилятора C3646

> «спецификатор»: Неизвестный спецификатор переопределения

## <a name="remarks"></a>Примечания

Компилятор обнаружил маркер в положение ожидал найти спецификатор переопределения, когда токен не был распознан компилятором.

Например если нераспознанный *описатель* — **_NOEXCEPT**, замените ключевое слово **noexcept**.

Дополнительные сведения см. в разделе [спецификаторы переопределения](../../windows/override-specifiers-cpp-component-extensions.md).

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