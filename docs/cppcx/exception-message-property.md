---
title: "Свойство Exception::Message | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Свойство Exception::Message"
ms.assetid: ad1199cd-0889-4803-ad0d-a3a7b3c51891
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Свойство Exception::Message
Сообщение с описанием ошибки.  
  
## Синтаксис  
  
```cpp  
public:property String^ Message;  
```  
  
## Значение свойства  
 В исключениях, создаваемых в среде выполнения Windows, это предоставляемое системой описание ошибки.  
  
## Заметки  
 В [!INCLUDE[win8](../cppcx/includes/win8-md.md)] это свойство доступно только для чтения, поскольку в этой версии среды выполнения Windows исключения передаются через интерфейс ABI только в виде значений HRESULTS. В [!INCLUDE[win81](../cppcx/includes/win81-md.md)] через интерфейс ABI передается более подробная информация об исключениях, и можно задать пользовательское сообщение, к которому другие компоненты могут обращаться программным образом. Дополнительные сведения см. в разделе [Исключения \(C\+\+\/CX\)](../cppcx/exceptions-c-cx.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::Exception](../cppcx/platform-exception-class.md)