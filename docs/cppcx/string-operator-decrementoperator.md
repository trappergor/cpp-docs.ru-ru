---
title: "Оператор String::operator+ | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator+"
dev_langs: 
  - "C++"
ms.assetid: 919b5ba4-3d3b-47a4-9893-9a9ce51fb9c8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор String::operator+
Указывает, равны ли значения двух указанных объектов [String](../cppcx/platform-string-class.md).  
  
## Синтаксис  
  
```cpp  
  
bool String::operator+( String^ str1,  
                         String^ str2)  
  
```  
  
#### Параметры  
 `str1`  
 Первый объект `String`.  
  
 `str2`  
 Второй объект `String`, содержимое которого будет добавлено в `str1`.  
  
## Возвращаемое значение  
 `true`, если значения параметров `str1` и `str2` равны; в противном случае — `false`.  
  
## Заметки  
 Этот оператор создает объект `String^`, содержащий данные из двух операндов. Используйте его для удобства, если производительность не играет решающей роли. Несколько вызовов "`+`" в функции, скорее всего, не будут иметь последствий, но если вы имеете дело с большими объектами или текстовыми данными в сложном цикле, используйте стандартные механизмы и типы C\+\+.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)