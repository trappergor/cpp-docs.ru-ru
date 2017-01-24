---
title: "CDataSource::OpenFromInitializationString | Microsoft Docs"
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
  - "CDataSource.OpenFromInitializationString"
  - "OpenFromInitializationString"
  - "CDataSource::OpenFromInitializationString"
  - "ATL::CDataSource::OpenFromInitializationString"
  - "ATL.CDataSource.OpenFromInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromInitializationString - метод"
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenFromInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Источник данных будет открыт определенный пользователем строкой для инициализации.  
  
## Синтаксис  
  
```  
  
      HRESULT OpenFromInitializationString(   
   LPCOLESTR szInitializationString,   
   bool fPromptForInfo = false    
) throw( );  
```  
  
#### Параметры  
 *szInitializationString*  
 \[in\] строка инициализации.  
  
 *fPromptForInfo*  
 \[in\] если данный аргумент имеет значение **true**, `OpenFromInitializationString` установит свойство **DBPROP\_INIT\_PROMPT** значение **DBPROMPT\_COMPLETEREQUIRED**, которое указывает, чтобы пользователь был предложено, только если требуются дополнительные сведения.  Это полезно в случаях, в которых строка инициализации определяет базу данных, которая требует пароля, но строка не содержит пароль.  Пользователю будет предложено ввести пароль \(или любого другого отсутствующих сведений\) при попытке подключения к базе данных.  
  
 Значение по умолчанию **false**, которое указывает, что пользователь никогда не будет предложено \(наборы **DBPROP\_INIT\_PROMPT** значение **DBPROMPT\_NOPROMPT**\).  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод будет открыт объект источника данных с помощью компонентов служб в oledb32.dll; эта библиотека DLL содержит реализацию функций компонентов службы, таких как создание пулов ресурсов, автоматическое зачисление транзакций и т д  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataSource](../Topic/CDataSource%20Class.md)