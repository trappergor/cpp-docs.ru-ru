---
title: Ошибка компилятора C2011 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09946a6a3e974293e65a582c735e3de42503f0c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115045"
---
# <a name="compiler-error-c2011"></a>Ошибка компилятора C2011

identifier: повторное определение типа type

Идентификатор ранее был определен как `type`. Проверьте переопределения идентификатора.

Ошибка C2011 также может возникнуть при импорте файла заголовков или библиотеки типов более одного раза в один файл. Для предотвращения нескольких включений типов, определенных в файле заголовка, используйте include guards или `#pragma` [после](../../preprocessor/once.md) директив в файле заголовка.

Если вам нужно найти исходное объявление переопределенного типа, можно использовать [/P](../../build/reference/p-preprocess-to-a-file.md) флаг компилятора для создания предварительно обработанные выходные данные, передаваемые компилятору. Вы можете воспользоваться средствами поиска текста для поиска экземпляров переопределенного идентификатора в выходном файле.

В следующем примере показано возникновение ошибки C2011 и приводятся сведения по ее устранению.

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```