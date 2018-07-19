---
title: Ошибка компилятора C2011 | Документы Microsoft
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
ms.openlocfilehash: 898a724f022a81f590ec1f8165de9752de6c1d0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166641"
---
# <a name="compiler-error-c2011"></a>Ошибка компилятора C2011
identifier: повторное определение типа type  
  
 Идентификатор ранее был определен как `type`. Проверьте переопределения идентификатора.  
  
 Ошибка C2011 также может возникнуть при импорте файла заголовков или библиотеки типов более одного раза в один файл. Для предотвращения нескольких включений типов, определенных в файле заголовка, используйте include guards или `#pragma` [после](../../preprocessor/once.md) директивы в файле заголовка.  
  
 Если требуется найти исходное объявление переопределенного типа, можно использовать [/P](../../build/reference/p-preprocess-to-a-file.md) флаг компилятора для создания предварительно обработанные выходные данные, передаваемые компилятору. Вы можете воспользоваться средствами поиска текста для поиска экземпляров переопределенного идентификатора в выходном файле.  
  
 В следующем примере показано возникновение ошибки C2011 и приводятся сведения по ее устранению.  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```