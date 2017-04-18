---
title: "Неустранимая ошибка C1037 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1037
dev_langs:
- C++
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 892ce10f7d19266ce45d559ce35bc82946887c52
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1037"></a>Неустранимая ошибка C1037
не удается открыть объектный файл "имя_файла"  
  
 Объектный файл, заданный путем [/Fo](../../build/reference/fo-object-file-name.md) не может быть открыт.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Недопустимое имя файла.  
  
2.  Недостаточно памяти для открытия файла.  
  
3.  Файл используется другим процессом.  
  
4.  Существует доступный только для чтения файл с таким же именем.  
  
 В Visual C++ .NET (версия компилятора 1300) существует ошибка, из-за которой необходимо правильно устанавливать языковой стандарт пользователя в том случае, если имя файла (или путь к нему) содержит символы в многобайтовой кодировке. Установки языкового стандарта системы недостаточно; для обработки символов в многобайтовой кодировке должен быть настроен языковой стандарт пользователя.
