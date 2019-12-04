---
title: Неустранимая ошибка C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 2f39359d55b5564c6379c84f07e942cf3484e011
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747414"
---
# <a name="fatal-error-c1071"></a>Неустранимая ошибка C1071

непредвиденное обнаружение конца файла в комментарии

Компилятор достиг конца файла при сканировании комментария.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Отсутствует признак конца комментария (*/).

1. Отсутствует символ новой строки после комментария в последней строке исходного файла.

Следующий пример приводит к возникновению ошибки C1071:

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
