---
title: Ошибка компилятора C2026 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 055ac47d036a1027817aa6b3433bfe0e2e88570e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019553"
---
# <a name="compiler-error-c2026"></a>Ошибка компилятора C2026

слишком большая строка, замыкающие знаки сокращены

Строка имеет больше времени, чем ограничение 16380 однобайтовых знаков.

До, объединяемых смежные строки строка не может быть длиннее 16380 однобайтовых символов.

Строка Юникода вдвое Эта длина также вызовет эту ошибку.

Если у вас есть строки, определенный следующим образом, он создает C2026:

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Может привести к нарушению его следующим образом:

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Вам может потребоваться сохранить чрезвычайно большого строковых литералов (32 КБ или больше) в настраиваемый ресурс или внешнего файла. См. в разделе [Создание нового настраиваемого ресурса или ресурса данных](../../windows/creating-a-new-custom-or-data-resource.md) Дополнительные сведения.