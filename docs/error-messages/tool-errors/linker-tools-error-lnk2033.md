---
title: Ошибка средств компоновщика LNK2033 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c547b4d35e2e7fe057cdd67f0dad47f58d000c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040000"
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