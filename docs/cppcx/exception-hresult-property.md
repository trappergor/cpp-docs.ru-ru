---
title: "Exception::HResult - свойство | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::HResult - свойство"
ms.assetid: 24ef008d-6884-4b8b-9556-41bfa6e1edf1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::HResult - свойство
Значение HRESULT, соответствующее исключению.  
  
## Синтаксис  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Значение свойства  
 Значение HRESULT.  
  
## Заметки  
 Большинство исключений создаются как ошибки модели COM, которые возвращаются в виде значений HRESULT. C\+\+\/CX преобразует эти значения в объекты Platform::Exception^, и это свойство сохраняет значение исходного кода ошибки.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::Exception](../cppcx/platform-exception-class.md)