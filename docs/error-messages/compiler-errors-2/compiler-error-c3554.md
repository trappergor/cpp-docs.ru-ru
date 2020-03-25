---
title: Ошибка компилятора C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: ecdb90e845714e046ed21cf5a200ef4548487df6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200607"
---
# <a name="compiler-error-c3554"></a>Ошибка компилятора C3554

"decltype" не может объединяться с любыми другими спецификаторами типа

Нельзя уточнить ключевое слово `decltype()` с помощью какого-либо описателя типа. Например, следующий фрагмент кода приводит к возникновению ошибки C3554.

```
int x;
unsigned decltype(x); // C3554
```
