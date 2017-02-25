---
title: "COleObjectFactory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class factories, COleObjectFactory class"
  - "COleObjectFactory class"
  - "создание объектов, OLE-объекты"
  - "объекты [C++], создание OLE"
  - "OLE class factory"
  - "OLE-объекты"
  - "OLE-объекты, создание"
  - "OLE, class factory"
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleObjectFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализующий фабрику классов OLE, которая создает объект OLE, как серверы, объекты автоматизации и документы.  
  
## Синтаксис  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleObjectFactory::COleObjectFactory](../Topic/COleObjectFactory::COleObjectFactory.md)|Создает объект `COleObjectFactory`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleObjectFactory::GetClassID](../Topic/COleObjectFactory::GetClassID.md)|Возвращает идентификатор класса объектов OLE эта фабрика создает.|  
|[COleObjectFactory::IsLicenseValid](../Topic/COleObjectFactory::IsLicenseValid.md)|Определяет, если лицензия элемента управления является допустимой.|  
|[COleObjectFactory::IsRegistered](../Topic/COleObjectFactory::IsRegistered.md)|Указывает, следует ли зарегистрирован фабрику объектов с OLE системные библиотеки DLL.|  
|[COleObjectFactory::Register](../Topic/COleObjectFactory::Register.md)|Регистрирует это фабрику объектов с OLE системные библиотеки DLL.|  
|[COleObjectFactory::RegisterAll](../Topic/COleObjectFactory::RegisterAll.md)|Регистрирует фабрики объектов всего приложения с OLE системные библиотеки DLL.|  
|[COleObjectFactory::Revoke](../Topic/COleObjectFactory::Revoke.md)|Отменяет регистрацию данной фабрики объекта с OLE системные библиотеки DLL.|  
|[COleObjectFactory::RevokeAll](../Topic/COleObjectFactory::RevokeAll.md)|Отменяет регистрацию объекта OLE фабрик приложения с системные библиотеки DLL.|  
|[COleObjectFactory::UnregisterAll](../Topic/COleObjectFactory::UnregisterAll.md)|Отменяет регистрацию всех фабрик объекта приложения.|  
|[COleObjectFactory::UpdateRegistry](../Topic/COleObjectFactory::UpdateRegistry.md)|Регистрирует это фабрику объектов OLE с реестром системы.|  
|[COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)|Регистрирует фабрики объектов OLE всего приложения с реестром системы.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleObjectFactory::GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)|Запрашивает уникальный ключ из библиотеки DLL элемента управления.|  
|[COleObjectFactory::OnCreateObject](../Topic/COleObjectFactory::OnCreateObject.md)|Вызываемый платформой для создания нового объекта типа этой фабрики.|  
|[COleObjectFactory::VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)|Проверяет, что ключ, внедренный в элементе управления соответствует ключу, внедренный в контейнере.|  
|[COleObjectFactory::VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)|Проверяет, что элемент управления лицензирован для использования во время разработки.|  
  
## Заметки  
 Класс `COleObjectFactory` содержит функции\-члены для выполнения следующих функций:  
  
-   Управление регистрацией объектов.  
  
-   Обновление OLE регистр системы, так же как и регистрация среды выполнения, которая сообщает OLE, что объекты выполнение и ее можно получать сообщения.  
  
-   Применение лицензирования путем ограничения использования элемента управления к лицензированным разработчикам во время разработки, так и к приложениям лицензированным во время выполнения.  
  
-   Регистрация фабрики объектов OLE управления с реестром системы.  
  
 Дополнительные сведения о создании объекта см. в разделе статьи [Объекты данных и источников данных \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md) и [Объекты данных и источников данных: создание и разрушение](../../mfc/data-objects-and-data-sources-creation-and-destruction.md).  Дополнительные сведения о регистрации см. в статье [регистрация](../../mfc/registration.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleObjectFactory`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)