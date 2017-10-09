---
title: "Ошибка компилятора C2011 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f32048e0de21e5af2d4d52a0c703813b1a1ff8b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
