---
title: "Оператор StringReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 03a33467-d65f-4508-bcb4-17d7cc99398f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор StringReference::operator=
Присваивает указанный объект текущему объекту `StringReference`.  
  
## Синтаксис  
  
```cpp  
  
   StringReference& operator=(const StringReference& __fstrArg);  
  
StringReference& operator=(const ::default::char16* __strArg);  
  
```  
  
#### Параметры  
 `__fstrArg`  
 Адрес объекта `StringReference`, используемый для инициализации текущего объекта `StringReference`.  
  
 `__strArg`  
 Указатель на массив значений char16, используемый для инициализации текущего объекта `StringReference`.  
  
## Возвращаемое значение  
 Ссылка на объект типа `StringReference`.  
  
## Заметки  
 Поскольку `StringReference` является стандартным классом C\+\+, а не ссылочным классом, он не отображается в **обозревателе объектов**.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)