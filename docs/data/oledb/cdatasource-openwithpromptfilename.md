---
title: "CDataSource::OpenWithPromptFileName | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource.OpenWithPromptFileName"
  - "OpenWithPromptFileName"
  - "ATL::CDataSource::OpenWithPromptFileName"
  - "ATL.CDataSource.OpenWithPromptFileName"
  - "CDataSource::OpenWithPromptFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithPromptFileName - метод"
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenWithPromptFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот метод отображает диалоговое окно, а затем открывает источник данных, используя указанный пользователем файл.  
  
## Синтаксис  
  
```  
  
        HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### Параметры  
 `hWnd`  
 \[входные данные\] Дескриптор окна, которое является родительским объектом диалогового окна.  
  
 `dwPromptOptions`  
 \[входные данные\] Определяет стиль отображаемого диалогового окна выбора.  Возможные значения см. в файле Msdasc.h.  
  
 *szInitialDirectory*  
 \[входные данные\] Исходный каталог для отображения в диалоговом окне выбора.  
  
## Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## Заметки  
 Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL\-библиотека содержит реализацию функций компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д.  Подробнее см. в разделе "Службы OLE DB" справочника программиста OLE DB на странице [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataSource](../Topic/CDataSource%20Class.md)