---
title: Ошибка компилятора C3707 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d18d4a82d06018cdba6147ba6756b1718648847a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052791"
---
# <a name="compiler-error-c3707"></a>Ошибка компилятора C3707

«функция»: метод disp-интерфейса должен иметь dispid

Если вы используете `dispinterface` метод, его значение необходимо присваивать `dispid`. Чтобы устранить эту ошибку, назначьте `dispid` для `dispinterface` метод, например, раскомментировав `id` атрибута метода в приведенном ниже примере. Дополнительные сведения см. в разделе атрибуты [disp-интерфейс](../../windows/dispinterface.md) и [идентификатор](../../windows/id.md).

Следующий пример приводит к возникновению ошибки C3707:

```
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```