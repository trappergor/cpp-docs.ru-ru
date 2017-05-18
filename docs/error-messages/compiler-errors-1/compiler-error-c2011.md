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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ed0aa8e9db0829716765128c9d409de9852808e1
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2011"></a>Ошибка компилятора C2011
identifier: повторное определение типа type  
  
 Идентификатор ранее был определен как `type`. Проверьте переопределения идентификатора.  
  
 Ошибка C2011 также может возникнуть при импорте файла заголовков или библиотеки типов более одного раза в один файл. Для предотвращения нескольких включений типов, определенных в файле заголовка, включать условия или `#pragma` [после](../../preprocessor/once.md) директивы в файле заголовка.  
  
 Если вам необходимо найти исходного объявления переопределенное типа, можно использовать [/P](../../build/reference/p-preprocess-to-a-file.md) флаг компилятора для создания предварительно обработанные выходные данные передаются компилятору. Вы можете воспользоваться средствами поиска текста для поиска экземпляров переопределенного идентификатора в выходном файле.  
  
 В следующем примере показано возникновение ошибки C2011 и приводятся сведения по ее устранению.  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```
