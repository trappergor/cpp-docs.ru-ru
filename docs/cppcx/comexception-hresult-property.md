---
title: "COMException::HResult - свойство | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMException::HResult - свойство"
ms.assetid: 53762ab5-ce71-4397-b7b4-8175741c838f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# COMException::HResult - свойство
Значение HRESULT, соответствующее исключению.  
  
## Синтаксис  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Значение свойства  
 Значение HRESULT, задающее ошибку.  
  
## Заметки  
 Дополнительные сведения об интерпретации значения HRESULT см. в разделе [Структура кодов ошибок модели COM](http://go.microsoft.com/fwlink/p/?LinkId=262045).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## Заголовок подраздела  
  
## См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)