---
title: "Неустранимая ошибка C1037 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c1f358201b36b73e1db41f2f72e1f92deb44f368
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1037"></a>Неустранимая ошибка C1037
не удается открыть объектный файл "имя_файла"  
  
 Не удается открыть объектный файл, заданный с помощью параметра [/Fo](../../build/reference/fo-object-file-name.md) .  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Недопустимое имя файла.  
  
2.  Недостаточно памяти для открытия файла.  
  
3.  Файл используется другим процессом.  
  
4.  Существует доступный только для чтения файл с таким же именем.  
  
 В Visual C++ .NET (версия компилятора 1300) существует ошибка, из-за которой необходимо правильно устанавливать языковой стандарт пользователя в том случае, если имя файла (или путь к нему) содержит символы в многобайтовой кодировке. Установки языкового стандарта системы недостаточно; для обработки символов в многобайтовой кодировке должен быть настроен языковой стандарт пользователя.
