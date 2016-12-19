---
title: "CSettingsStoreSP Class | Microsoft Docs"
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
  - "CSettingsStoreSP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStoreSP class"
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSettingsStoreSP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CSettingsStoreSP` вспомогательный класс, который можно использовать для создания экземпляров [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).  
  
## Синтаксис  
  
```  
class CSettingsStoreSP  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSettingsStoreSP::CSettingsStoreSP](../Topic/CSettingsStoreSP::CSettingsStoreSP.md)|Создает объект `CSettingsStoreSP`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSettingsStoreSP::Create](../Topic/CSettingsStoreSP::Create.md)|Создает экземпляр класса, производного от `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](../Topic/CSettingsStoreSP::SetRuntimeClass.md)|Устанавливает класса среды выполнения.  Метод `Create` использует класса среды выполнения для определения, какой класс объекта, который необходимо создать.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|`m_dwUserData`|Пользовательский пользователь, который хранится в объекте `CSettingsStoreSP`.  Эти данные указываются в конструкторе объекта `CSettingsStoreSP`.|  
|`m_pRegistry`|`CSettingsStore` производный объект, метод `Create` создать.|  
  
## Заметки  
 Можно использовать класс `CSettingsStoreSP`, чтобы перенаправлять все операции реестра MFC на другие расположения в XML\-файл или базы данных.  Для этого выполните следующие действия:  
  
1.  Создайте класс \(например `CMyStore`\) и наследуйте его из `CSettingsStore`.  
  
2.  Используйте макрос [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) и [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) с пользовательским классом `CSettingsStore` чтобы включить динамическое создание.  
  
3.  Переопределите и реализуйте `Read` виртуальные функции, функции и `Write` в пользовательском классе.  Реализуйте любой другой функции для считывания и записи данных в нужное место.  
  
4.  В приложении, вызовите `CSettingsStoreSP::SetRuntimeClass` и передайте указатель на [CRuntimeClass Structure](../Topic/CRuntimeClass%20Structure.md), полученный от класса.  
  
 Как правило, когда границы, что и к реестру, они будут теперь динамически создать экземпляр пользовательского класса и использовать их для чтения или записи данных.  
  
 `CSettingsStoreSP::SetRuntimeClass` использует глобальную статическую переменную.  Следовательно, только один из пользовательского хранилища доступен.  
  
## Требования  
 **заголовок:** afxsettingsstore.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)