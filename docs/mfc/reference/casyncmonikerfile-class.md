---
title: "CAsyncMonikerFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAsyncMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], асинхронный"
  - "asynchronous controls [C++]"
  - "CAsyncMonikerFile class"
  - "IMoniker interface, привязка"
  - "monikers [C++], MFC - библиотека"
  - "элементы управления OLE [C++], асинхронный"
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAsyncMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности для использования асинхронных моникеров в элементах управления ActiveX \(ранее OLE элементах управления\).  
  
## Синтаксис  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](../Topic/CAsyncMonikerFile::CAsyncMonikerFile.md)|Создает объект `CAsyncMonikerFile`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAsyncMonikerFile::Close](../Topic/CAsyncMonikerFile::Close.md)|Закрывает и освобождает все ресурсы.|  
|[CAsyncMonikerFile::GetBinding](../Topic/CAsyncMonikerFile::GetBinding.md)|Извлекает указатель на привязке асинхронной передачи.|  
|[CAsyncMonikerFile::GetFormatEtc](../Topic/CAsyncMonikerFile::GetFormatEtc.md)|Извлекает формат данных в потоке.|  
|[CAsyncMonikerFile::Open](../Topic/CAsyncMonikerFile::Open.md)|Открывает файл в асинхронном режиме.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](../Topic/CAsyncMonikerFile::CreateBindStatusCallback.md)|Создает COM\-объект, что средства `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](../Topic/CAsyncMonikerFile::GetBindInfo.md)|Именем OLE библиотекой системы для запроса, что сведения о типе был создано привязки.|  
|[CAsyncMonikerFile::GetPriority](../Topic/CAsyncMonikerFile::GetPriority.md)|Именем OLE библиотекой системы, чтобы получить приоритет привязки.|  
|[CAsyncMonikerFile::OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)|Вызываемый для предоставления данных по мере того, как она становится доступной на клиент во время асинхронной операции привязки.|  
|[CAsyncMonikerFile::OnLowResource](../Topic/CAsyncMonikerFile::OnLowResource.md)|Вызываемый при низки ресурсы.|  
|[CAsyncMonikerFile::OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)|Вызываемый для отображения хода выполнения в процессе загрузки данных.|  
|[CAsyncMonikerFile::OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)|Вызываемый, когда привязка запуск.|  
|[CAsyncMonikerFile::OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)|Вызываемый, когда асинхронная передача остановлено.|  
  
## Заметки  
 Производный от [CMonikerFile](../Topic/CMonikerFile%20Class.md), который, в свою очередь, является производным от [COleStreamFile](../Topic/COleStreamFile%20Class.md), `CAsyncMonikerFile` использует интерфейс [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) для доступа к любой поток данных асинхронно, включая файлы загрузки в асинхронном режиме из url\-адреса.  Файлы могут быть свойствами datapath элементов управления ActiveX.  
  
 Асинхронные моникеры используются главным образом в Интернет\- разрешенных приложениях и элементах управления ActiveX предоставить отзывчивый интерфейс пользователя во время передачи файла.  Блестящий пример использования [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) предоставить асинхронные свойств для элементов управления ActiveX.  Обращаются, что обратный вызов для указания на объект `CDataPathProperty` повторно доступность новых данных во время длинномерного процесса обмена свойства.  
  
 Дополнительные сведения о том, как использовать асинхронные моникеры и управления ActiveX в приложениях веб\-частей см. в следующих статьях:  
  
-   [Первые шаги в интернете. асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Первые шаги в интернете. Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 `CAsyncMonikerFile`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [CMonikerFile Class](../Topic/CMonikerFile%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMonikerFile Class](../Topic/CMonikerFile%20Class.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Asynchronous Versus Synchronous Monikers](http://msdn.microsoft.com/library/windows/desktop/ms687193)