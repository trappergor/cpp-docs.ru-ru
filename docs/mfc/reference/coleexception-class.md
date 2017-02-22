---
title: "COleException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleException class"
  - "исключения, OLE"
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет состояние исключения, относящиеся к OLE операции.  
  
## Синтаксис  
  
```  
class COleException : public CException  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleException::Process](../Topic/COleException::Process.md)|Преобразует обнаружено исключение в OLE кодом возврата.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleException::m\_sc](../Topic/COleException::m_sc.md)|Содержит код состояния, обозначающий причину исключения.|  
  
## Заметки  
 Класс `COleException` включает общий член данных, содержащий код состояния, указывающий причину исключения.  
  
 В общем случае не следует создать объект `COleException` напрямую; вместо этого необходимо вызвать [AfxThrowOleException](../Topic/AfxThrowOleException.md).  
  
 Дополнительные сведения об исключениях см. в разделе статьи [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md) и [исключения: OLE исключения](../Topic/Exceptions:%20OLE%20Exceptions.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [Пример CALCDRIV MFC](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)