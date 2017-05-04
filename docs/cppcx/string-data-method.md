---
title: "Метод String::Data | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Data"
ms.assetid: 9be4e015-dfb8-431e-a252-8498bd833f03
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::Data
Возвращает указатель на начало буфера данных объекта в качестве массива элементов `char16` \(`wchar_t`\) в стиле языка C.  
  
## Синтаксис  
  
```  
const char16* Data()  
```  
  
## Возвращаемое значение  
 Указатель на начало массива `const``char16` символов Юникода \(`char16` — определение типа \(typedef\) для `wchar_t`\).  
  
## Заметки  
 Используйте этот метод для преобразования из `Platform::String^` в `wchar_t*`. Когда объект `String` выходит за пределы области, указатель Data больше не является гарантированно допустимым. Чтобы сохранить данные после истечения времени жизни исходного объекта `String`, используйте [wcscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) для копирования массива в память, которую вы выделили самостоятельно.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)   
 [Метод String::Begin](../cppcx/string-begin-method.md)