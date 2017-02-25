---
title: "CDumpContext Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDumpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxDump object"
  - "CDumpContext class"
  - "диагностика, diagnostic classes"
  - "diagnostic classes"
  - "диагностика, diagnostic classes"
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDumpContext Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обозреватель поток\- ориентировали диагностический выход в форме людск\- четкого текста.  
  
## Синтаксис  
  
```  
class CDumpContext  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDumpContext::CDumpContext](../Topic/CDumpContext::CDumpContext.md)|Создает объект `CDumpContext`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDumpContext::DumpAsHex](../Topic/CDumpContext::DumpAsHex.md)|Создает дамп указанный элемент в шестнадцатеричном формате.|  
|[CDumpContext::Flush](../Topic/CDumpContext::Flush.md)|Сбрасывает все данные в буфере контекст дампа.|  
|[CDumpContext::GetDepth](../Topic/CDumpContext::GetDepth.md)|Возвращает целое число, соответствующее глубине дампа.|  
|[CDumpContext::HexDump](../Topic/CDumpContext::HexDump.md)|Байты дампов, содержащегося в массиве в шестнадцатеричном формате.|  
|[CDumpContext::SetDepth](../Topic/CDumpContext::SetDepth.md)|Устанавливает глубину дампа.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDumpContext::operator \<\<](../Topic/CDumpContext::operator%20%3C%3C.md)|Переменные и объекты вставок в контекст дампа.|  
  
## Заметки  
 `CDumpContext` не имеет базовый класс.  
  
 Можно использовать [afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md), predeclared объект `CDumpContext`, для большинства свой сбрасывать.  Объект `afxDump` доступен только в отладочной версии библиотеки Microsoft Foundation Class.  
  
 Некоторые использования `afxDump`[диагностические службы](../Topic/Diagnostic%20Services.md) памяти для вывода.  
  
 В области среда системы windows, выход из стандартного объекта `afxDump`, по существу примерно в поток `cerr`, направляется к отладчику с помощью функции Windows **OutputDebugString**.  
  
 Класс `CDumpContext` имеет перегруженный оператор вставки \(**\<\<**\) для указателей `CObject`, который создает дамп данные объекта.  Если требуется пользовательский формат дампа для производного объекта, переопределите [CObject::Dump](../Topic/CObject::Dump.md).  Большинство основу средство Microsoft классифицирует переопределенный функцию\-член `Dump`.  
  
 Классы, которые наследуются от `CObject`, как `CString`, `CTime` и `CTimeSpan`, имеют собственные перегруженные операторы insert `CDumpContext`, как делают часто\-, используемые в макете **CFileStatus**, `CPoint` и `CRect`.  
  
 При использовании [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) или макрос [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) в реализации данного класса, `CObject::Dump` напечатает имя `CObject`\- производный класс.  В противном случае он `CObject` напечатает.  
  
 Класс `CDumpContext` доступен и версии отладки и выпуска библиотеки, но функцию\-член `Dump` указан только в отладочной версии.  Используйте **\#ifdef \_DEBUG** \/выписки `#endif` чтобы отыскать вилку в диагностический код, включая пользовательские функции\-члены `Dump`.  
  
 Прежде чем создать собственный объект `CDumpContext`, необходимо создать объект `CFile`, который служит в качестве назначения дампа.  
  
 Дополнительные сведения о `CDumpContext` см. в разделе [Отладка приложений MFC](../Topic/MFC%20Debugging%20Techniques.md).  
  
 **\#define \_DEBUG**  
  
## Иерархия наследования  
 `CDumpContext`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../Topic/CObject%20Class.md)