---
title: Ошибка компилятора C3646 | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c038520c1a35fa5264e1e98b074687efb336d028
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "35658615"
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