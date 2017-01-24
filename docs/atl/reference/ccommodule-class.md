---
title: "CComModule Class | Microsoft Docs"
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
  - "CComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComModule class"
  - "DLL modules [C++], ATL - библиотека"
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Из библиотеки ATL 7,0, `CComModule` нерекомендуемо: дополнительные сведения см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
class CComModule : public _ATL_MODULE  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComModule::GetClassObject](../Topic/CComModule::GetClassObject.md)|Создает объект указанного идентификатора CLSID.  Только для DLLs.|  
|[CComModule::GetModuleInstance](../Topic/CComModule::GetModuleInstance.md)|Возвращает `m_hInst`.|  
|[CComModule::GetResourceInstance](../Topic/CComModule::GetResourceInstance.md)|Возвращает `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](../Topic/CComModule::GetTypeLibInstance.md)|Возвращает `m_hInstTypeLib`.|  
|[CComModule::Init](../Topic/CComModule::Init.md)|Инициализирует элементы данных.|  
|[CComModule::RegisterClassHelper](../Topic/CComModule::RegisterClassHelper.md)|Представляет регистрацию класса объекта стандартную в реестре системы.|  
|[CComModule::RegisterClassObjects](../Topic/CComModule::RegisterClassObjects.md)|Регистрирует объект класса.  Для Exe.|  
|[CComModule::RegisterServer](../Topic/CComModule::RegisterServer.md)|Обновляет реестру системы для каждого объекта в сопоставлении объекта.|  
|[CComModule::RegisterTypeLib](../Topic/CComModule::RegisterTypeLib.md)|Регистрирует библиотеки типов.|  
|[CComModule::RevokeClassObjects](../Topic/CComModule::RevokeClassObjects.md)|Отменяет объекта класса.  Для Exe.|  
|[CComModule::Term](../Topic/CComModule::Term.md)|Освобождает элементы данных.|  
|[CComModule::UnregisterClassHelper](../Topic/CComModule::UnregisterClassHelper.md)|Удаляет регистрацию класса объекта стандартная из системного реестра.|  
|[CComModule::UnregisterServer](../Topic/CComModule::UnregisterServer.md)|Отменяет регистрацию каждый объект в сопоставлении объекта.|  
|[CComModule::UpdateRegistryClass](../Topic/CComModule::UpdateRegistryClass.md)|Регистрирует и отменяет регистрацию объекта стандартная регистрации класса.|  
|[CComModule::UpdateRegistryFromResourceD](../Topic/CComModule::UpdateRegistryFromResourceD.md)|Запускает скрипт, содержащегося в указанном ресурсе для регистрации и отмены регистрации объект.|  
|[CComModule::UpdateRegistryFromResourceS](../Topic/CComModule::UpdateRegistryFromResourceS.md)|Статически скомпонована в компонент реестра библиотеки ATL.  Запускает скрипт, содержащегося в указанном ресурсе для регистрации и отмены регистрации объект.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComModule::m\_csObjMap](../Topic/CComModule::m_csObjMap.md)|Ensures синхронизировал доступ к данным сопоставления объекта.|  
|[CComModule::m\_csTypeInfoHolder](../Topic/CComModule::m_csTypeInfoHolder.md)|Ensures синхронизировал доступ к данным библиотеки типов.|  
|[CComModule::m\_csWindowCreate](../Topic/CComModule::m_csWindowCreate.md)|Ensures синхронизировал доступ к данным класса окна и статическим данным, используемым во время создания окна.|  
|[CComModule::m\_hInst](../Topic/CComModule::m_hInst.md)|Содержит дескриптор для экземпляра модуля.|  
|[CComModule::m\_hInstResource](../Topic/CComModule::m_hInstResource.md)|По умолчанию содержит дескриптор для экземпляра модуля.|  
|[CComModule::m\_hInstTypeLib](../Topic/CComModule::m_hInstTypeLib.md)|По умолчанию содержит дескриптор для экземпляра модуля.|  
|[CComModule::m\_pObjMap](../Topic/CComModule::m_pObjMap.md)|Указывает на сопоставление объекта поддерживаемому модулем приводят в примере.|  
  
## Заметки  
  
> [!NOTE]
>  Этот класс не рекомендуем и мастера создания кода библиотеки ATL сейчас используют производные классы [Класса CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md).  Дополнительные сведения см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  Сведения, которые следуют для использования с приложения, созданные с предыдущими выпусками библиотеки ATL.  `CComModule` все еще является частью библиотеки ATL для назад.  
  
 `CComModule` реализующий модуль сервера модели COM, что клиент для доступа к компонентам модуля.  `CComModule` поддерживает как модуль библиотеки DLL \(в процессе\) и EXE \(локальных\).  
  
 Экземпляр `CComModule` использует сопоставление объекта для поддержания набора определений объекта класса.  Это сопоставление объекта реализуется как массив структур `_ATL_OBJMAP_ENTRY` и содержит сведения для:  
  
-   Вставка и удаление описания объекта в реестре системы.  
  
-   Создав объекты через фабрику класса.  
  
-   Установление связи между клиентом и объектом корневого действия в компоненте.  
  
-   Управление временем существования объектов для класса.  
  
 При запуске модели COM AppWizard библиотеки ATL мастер автоматически создает `_Module` глобальный экземпляр `CComModule` или класс, производный от него.  Дополнительные сведения о мастере проекта библиотеки ATL см. в статье [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md).  
  
 В дополнение к `CComModule` библиотеки ATL предоставляет [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), реализующий модуль Exe и модели изоляции для служб Windows.  Создайте модуль с `CComAutoThreadModule`, когда нужно создать объекты в нескольких подразделениях.  
  
## Иерархия наследования  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## Требования  
 `Header:` atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)