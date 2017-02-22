---
title: "Извлечение члена библиотеки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXTRACT - параметр управления библиотекой"
  - "EXTRACT - параметр управления библиотекой"
  - "-EXTRACT - параметр управления библиотекой"
  - "извлечение членов библиотеки"
  - "LIB [C++], извлечение членов библиотеки"
  - "библиотеки, извлечение членов"
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Извлечение члена библиотеки
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для создания файла объекта \(.OBJ\), содержащего копию члена существующей библиотеки, можно воспользоваться переменной LIB.  Чтобы извлечь копию члена, используйте следующий синтаксис.  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Эта команда создает OBJ\-файл с именем *objectfile*, содержащий копию члена `member` *библиотеки*.  Имя члена `member` задается с учетом регистра.  Одна команда извлекает только один член.  Требуется параметр \/OUT; имени выхода по умолчанию не существует.  Если файл с именем *objectfile* уже существует в указанном каталоге \(или в текущем каталоге, если для *objectfile* не указано никакого каталога\), извлеченный файл *objectfile* заменяет существующий файл.  
  
## См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)