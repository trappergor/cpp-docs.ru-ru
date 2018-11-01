---
title: Ошибка средств компоновщика LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 7e95823e23215848ff3e5d201171523c9009eb2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571890"
---
# <a name="linker-tools-error-lnk2033"></a>Ошибка средств компоновщика LNK2033

неразрешенная лексема typeref (маркер) для «тип»

Тип не имеет определения в метаданных MSIL.

Ошибка LNK2033 может возникнуть при компиляции с параметром **/CLR: safe** и где имеется опережающее объявление типа в модуле MSIL, где находятся ссылки на тип в модуле MSIL.

Тип должен быть определен в разделе **/CLR: safe**.

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка LNK2033.

```
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```