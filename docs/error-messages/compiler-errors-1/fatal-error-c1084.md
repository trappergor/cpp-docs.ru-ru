---
title: "Неустранимая ошибка C1084 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: caf1e64e91871087c9e47860a41c2824a811295a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1084"></a>Неустранимая ошибка C1084
Не удается прочесть файл "типфайла": "файл": сообщение  
  
 Эта ошибка обычно является результатом сбоя при вызове внутреннего системного API, выполненного компилятором. Сообщение, показанное при обнаружении этой ошибки часто создаются либо [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) или [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 Выполнение указанных ниже действий может помочь устранить ошибку C1084.  
  
-   Убедитесь в том, что указанный файл существует.  
  
-   Убедитесь в том, что для доступа к указанному файлу заданы соответствующие разрешения.  
  
-   Убедитесь в синтаксисе командной строки соответствует правилам, указанным в разделе [синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md).  
  
-   Убедитесь, что переменные среды **TMP** и **TEMP** были правильно набора, а также соответствующие разрешения для доступа к каталогам, эти переменные среды ссылаются. Также убедитесь, что диски, на который указывает **TMP** и **TEMP** переменных среды содержит достаточный объем свободного места.  
  
-   Если в сообщении говорится "неверный номер файла", указанный файл мог быть закрыт на переднем плане во время компиляции в фоновом режиме.  
  
 Завершив описанную выше диагностику, выполните чистую сборку.
