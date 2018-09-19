---
title: Неустранимая ошибка C1004 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a284de510fde49602a06fb9282c0ddd59eeb0ac1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020293"
---
# <a name="fatal-error-c1004"></a>Неустранимая ошибка C1004

Неожиданный конец файла найден

Компилятор достиг конца исходного файла без разрешения конструктора. Код может отсутствовать один из следующих элементов:

- Закрывающую фигурную скобку

- Закрывающая скобка

- Метка, комментария закрытия (* /)

- Точка с запятой

Чтобы устранить эту ошибку, проверьте следующее:

- Жесткий диск по умолчанию будет недостаточно места для временных файлов, которые требуется примерно вдвое больше места, что и исходный файл.

- `#if` , Результатом является значение false, отсутствует закрывающая директива `#endif` директива.

- Исходный файл не заканчивается возврат каретки и перевода строки.

Следующий пример приводит к возникновению ошибки C1004:

```
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Возможное решение

```
// C1004b.cpp
#if TEST
#endif

int main() {}
```