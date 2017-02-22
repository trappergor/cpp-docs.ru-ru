---
title: "CCommand::Create | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.Create"
  - "CCommand::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create - метод [C++]"
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CCommand::Create
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает метод [CCommand::CreateCommand](../Topic/CCommand::CreateCommand.md), чтобы создать команду для указанного сеанса, а затем вызывает метод [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx), чтобы указать текст команды.  
  
## Синтаксис  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### Параметры  
 `session`  
 \[in\] сеанс, в котором a, чтобы создать команду.  
  
 `wszCommand`  
 \[in\] указатель на текст юникода командной строки.  
  
 `szCommand`  
 \[in\] указатель на текст ANSI командной строки.  
  
 `guidCommand`  
 \[in\] идентификатор GUID, определяющий синтаксис и общие правила для поставщика использовать при анализе текст команды.  Описание диалектов см. в разделе [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) справочника *программиста OLE DB*.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Первая форма **Создать** принимает командную строку юникода.  Вторая форма **Создать** принимает командную строку ANSI \(для для обратной совместимости с существующими приложениями ANSI\).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)