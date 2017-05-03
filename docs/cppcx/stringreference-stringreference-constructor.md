---
title: "Конструктор StringReference::StringReference | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 87dd9201-e638-4913-b37c-7091ae3f91ea
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор StringReference::StringReference
Инициализирует новый экземпляр класса `StringReference`.  
  
## Синтаксис  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
#### Параметры  
 `__fstrArg`  
 Объект `StringReference`, данные которого используются для инициализации нового экземпляра.  
  
 `__strArg`  
 Указатель на массив значений char16, используемый для инициализации нового экземпляра.  
  
 `__lenArg`  
 Число элементов в `__strArg`.  
  
## Заметки  
 Первая версия этого конструктора является конструктором по умолчанию. Вторая версия инициализирует новый экземпляра класса `StringReference` из объекта, заданного параметром `__fstrArg`. Третья и четвертая перегрузки инициализируют новый экземпляр класса `StringReference` из массива значений char16. char16 представляет 16\-разрядный текстовый символ ЮНИКОДА.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)