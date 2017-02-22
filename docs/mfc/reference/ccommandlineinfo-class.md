---
title: "CCommandLineInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCommandLineInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application flags [C++]"
  - "argv argument"
  - "CCommandLineInfo class"
  - "командная строка, синтаксический разбор"
  - "синтаксический разбор, аргументы командной строки"
  - "код запуска, parsing command-line arguments"
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCommandLineInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Помощь в анализ командной строки при запуске приложения.  
  
## Синтаксис  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCommandLineInfo::CCommandLineInfo](../Topic/CCommandLineInfo::CCommandLineInfo.md)|Создает объект по умолчанию `CCommandLineInfo`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCommandLineInfo::ParseParam](../Topic/CCommandLineInfo::ParseParam.md)|Переопределите этот обратный вызов для синтаксического анализа отдельные параметры.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md)|Указывает, что параметр **\/Automation** командной строки был найден.|  
|[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md)|Указывает, что параметр **\/Embedding** командной строки был найден.|  
|[CCommandLineInfo::m\_bShowSplash](../Topic/CCommandLineInfo::m_bShowSplash.md)|Указывает, экран\-заставка должна отображаться.|  
|[CCommandLineInfo::m\_nShellCommand](../Topic/CCommandLineInfo::m_nShellCommand.md)|Указывает команду оболочки.|  
|[CCommandLineInfo::m\_strDriverName](../Topic/CCommandLineInfo::m_strDriverName.md)|Отображает имя драйвера, если команда печать в оболочку; в противном случае пустой.|  
|[CCommandLineInfo::m\_strFileName](../Topic/CCommandLineInfo::m_strFileName.md)|Указывает напечатанное имя файла, который необходимо открыть или; пусто, если команда оболочки является новой или DDE.|  
|[CCommandLineInfo::m\_strPortName](../Topic/CCommandLineInfo::m_strPortName.md)|Отображает имя порта, если команда печать в оболочку; в противном случае пустой.|  
|[CCommandLineInfo::m\_strPrinterName](../Topic/CCommandLineInfo::m_strPrinterName.md)|Отображает имя принтера, если команда печать в оболочку; в противном случае пустой.|  
|[CCommandLineInfo::m\_strRestartIdentifier](../Topic/CCommandLineInfo::m_strRestartIdentifier.md)|Отображает уникальный идентификатор перезапуска диспетчера перезапуска, если диспетчер перезапуска перезагрузил приложение.|  
  
## Заметки  
 Обычно приложение MFC создает локальный экземпляр этого класса, в функции [InitInstance](../Topic/CWinApp::InitInstance.md) его объектов приложения.  Затем этот объект передается [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md), который вызывает повторно [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) для заполнения объекта `CCommandLineInfo`.  Объект `CCommandLineInfo` затем передается [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md) для обработки аргументов и флаги командной строки.  
  
 Этот объект можно использовать для инкапсуляции следующие параметры командной строки и параметры.  
  
|Аргумент командной строки|Команда выполнена|  
|-------------------------------|-----------------------|  
|*приложение*|Новый файл.|  
|Имя файла *приложения*|Открыть файл.|  
|Имя файла **\/p***приложения*|Файл печать на принтере по умолчанию.|  
|Порт драйвера принтера имени файла **\/pt***приложения*|Файл печати в указанном принтере.|  
|*приложение* **\/dde**|Запуске и подождите команда DDE.|  
|*приложение* **\/Automation**|Запуске сервера ole\-автоматизации.|  
|*приложение* **\/Embedding**|Правка до начала внедренный элемент OLE.|  
|*приложение* **\/Register**<br /><br /> *приложение* **\/Regserver**|Сообщает приложению выполнять все задачи регистрации.|  
|*приложение* **\/Unregister**<br /><br /> *приложение* **\/Unregserver**|Информирует приложение выполнять все задачи ООН\- регистрации.|  
  
 Создайте новый класс, производный от `CCommandLineInfo` чтобы обрабатывать другие флаги и значения параметров.  Переопределение [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) для обработки новых флаги.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CCommandLineInfo`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)   
 [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)