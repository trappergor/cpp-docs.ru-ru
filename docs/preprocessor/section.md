---
title: "section | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section_CPP"
  - "vc-pragma.section"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "прагмы, section"
  - "прагма раздела"
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# section
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает раздел в OBJ\-файле.  
  
## Синтаксис  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## Заметки  
 Термины *сегмент* и *раздел* в этом разделе взаимозаменимы.  
  
 После определения раздел остается допустимым для остальной части компиляции.  Однако следует использовать [\_\_declspec\(allocate\)](../Topic/allocate.md), так как иначе никакие данные не будут помещены в раздел.  
  
 *section\-name* — обязательный параметр, который будет именем раздела.  Имя не должно конфликтовать со стандартными именами раздела.  Список имен, которые не следует использовать при создании раздела, см. в разделе [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 `attributes` — необязательный параметр, состоящий из одного или нескольких разделенных запятыми атрибутов, которые требуется присвоить разделу.  Ниже перечислены возможные `attributes`.  
  
 **read \(чтение\)**  
 Позволяет выполнять операции чтения данных.  
  
 **write \(запись\)**  
 Позволяет выполнять операции записи данных.  
  
 **execute**  
 Позволяет выполнять код.  
  
 **shared**  
 Предоставляет совместный доступ к разделу всем процессам, загружающим образ.  
  
 **nopage**  
 Отмечает раздел как невыгружаемый; используются для драйверов устройств Win32.  
  
 **nocache**  
 Отмечает раздел как некэшируемый; используются для драйверов устройств Win32.  
  
 **discard**  
 Отмечает раздел как удаляемый; используются для драйверов устройств Win32.  
  
 **remove**  
 Отмечает раздел как нерезидентный; только драйверы виртуальных устройств \(V*x*D\).  
  
 Если не задать атрибуты, раздел будет иметь атрибуты чтения и записи.  
  
## Пример  
 В следующем примере первая инструкция определяет раздел и его атрибуты.  Целое число `j` не помещается в `mysec`, поскольку оно не было объявлено с `__declspec(allocate)`; `j` переходит в раздел данных.  Целое число `i` переходит в `mysec` как результат атрибута класса хранения `__declspec(allocate)`.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)