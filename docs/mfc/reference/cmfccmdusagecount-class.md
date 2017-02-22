---
title: "CMFCCmdUsageCount Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCmdUsageCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCmdUsageCount class"
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCCmdUsageCount Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отслеживает объем прием сообщений Windows, например, когда пользователь выбирает элемент из меню.  
  
## Синтаксис  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCCmdUsageCount::AddCmd](../Topic/CMFCCmdUsageCount::AddCmd.md)|Увеличивает на единицу счетчик, который связан с данной командой.|  
|[CMFCCmdUsageCount::GetCount](../Topic/CMFCCmdUsageCount::GetCount.md)|Получает количество потребления, который связан с указанным идентификатором команды|  
|[CMFCCmdUsageCount::HasEnoughInformation](../Topic/CMFCCmdUsageCount::HasEnoughInformation.md)|Определяет, является ли данный объект собирал минимальный объем данных отслеживания.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](../Topic/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd.md)|Указывает, используется ли заданную команду часто.|  
|[CMFCCmdUsageCount::Reset](../Topic/CMFCCmdUsageCount::Reset.md)|Очищает количество прием всех команд.|  
|[CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)|Считывает этот объект из архива или записывает его в архив.  \(Переопределяет [CObject::Serialize](../Topic/CObject::Serialize.md)\).|  
|[CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)|Задает значения общих элементов данных класса `CMFCCmdUsageCount`.|  
  
### Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`m_CmdUsage`|Объект `CMap`, в котором содержится сопоставление команды к их потреблению учитывается.|  
|`m_nMinUsagePercentage`|Минимальный процент потребления для команды часто должны использоваться.|  
|`m_nStartCount`|Счетчик начала, используемый для определения собирал, является ли данный объект минимальный объем данных отслеживания.|  
|`m_nTotalUsage`|Количество всех отслеживаемых команд.|  
  
### Заметки  
 Класс `CMFCCmdUsageCount` сопоставляет каждый числовой идентификатор сообщения Windows для счетчика 32 разрядное целое число без знака.  `CMFCToolBar` использует этот класс для отображения част\- используемых элементов панели инструментов.  Дополнительные сведения о `CMFCToolBar` см. в разделе [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  
  
 Можно ввести данные класса `CMFCCmdUsageCount` между запусками агента программы.  Используйте метод [CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md) для сериализации данных члена класса и метод [CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md) чтобы установить общие сведения о члене.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## Требования  
 **заголовок:** afxcmdusagecount.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)