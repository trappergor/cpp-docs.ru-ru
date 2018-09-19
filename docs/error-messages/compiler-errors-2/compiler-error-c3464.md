---
title: Ошибка компилятора C3464 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3464
dev_langs:
- C++
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05322479c076bbb929b6c742fdd379414a263376
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096591"
---
# <a name="compiler-error-c3464"></a>Ошибка компилятора C3464

"тип": вложенный тип переадресовывать невозможно

Перенаправление типов не применимо к вложенным типам.

Дополнительные сведения см. в разделе [Переадресация типа (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3464:

```
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```