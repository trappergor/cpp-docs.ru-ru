---
title: "Шаблон проекта библиотеки классов WRL | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаблон проекта библиотеки классов WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании Visual Studio для создания проекта [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\), можно значительно упростить задачу, загрузив шаблон проекта библиотеки классов WRL.  
  
> [!NOTE]
>  Если необходимо вручную обновить параметры проекта для существующего проекта, см. [DLL \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## Загрузите Шаблон проекта WRL.  
 Visual Studio не предоставляет шаблон для проектов [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  Здесь описано, как загрузить шаблон проекта, создающего базовую библиотеку классов для приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] с [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  
  
#### Загрузка Шаблона проекта WRL.  
  
1.  В строке меню выберите **Файл**, **Создать проект**.  
  
2.  В левой области диалогового окна **Создать проект** выберите **В сети**, а затем выберите **Шаблоны**.  
  
3.  В поле **Найти шаблоны в Интернете** в правом верхнем углу введите `Библиотека классов WRL`.  Когда шаблон появится в результатах поиска, нажмите кнопку **ОК**.  
  
4.  В диалоговом окне **Загрузить и установить**, если вы принимаете условия лицензии, нажмите кнопку **Установить**.  
  
5.  После того как шаблон установлен, создайте проект, выбрав **Файл**, **Создать проект**, а затем выбрав шаблон `WRLClassLibrary`.  Проект создает DLL.  
  
## Примеры, использующие шаблон проекта  
 Ознакомьтесь с разделом [Пошаговое руководство. Создание базового компонента среды выполнения Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) для получения примера, использующий этот шаблон для создания компонента [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Что предоставляет шаблон проекта  
 Шаблон проекта предоставляет:  
  
-   файл .idl, который объявляет атрибуты MIDL базового интерфейса его реализации класса.  Ниже приведен пример.  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   файл .cpp, определяющий реализацию класса.  Ниже приведен пример.  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     Базовый класс [RuntimeClass](../windows/runtimeclass-class.md) помогает управлять глобальной ссылкой всех объектов в модуле и объявляет методы интерфейсов [IUnknown](http://msdn.microsoft.com/ru-ru/33f1d79a-33fc-4ce5-a372-e08bda378332) и [IInspectable](http://msdn.microsoft.com/ru-ru/0657e51f-d4c0-46c6-927d-b01e54b6846c).  Макрос [InspectableClass](../windows/inspectableclass-macro.md) реализует `IUnknown` и `IInspectable`.  Макрос [ActivatableClass](../Topic/ActivatableClass%20Macros.md) создает фабрику класса, которая создает экземпляры классов.  
  
-   файл с именем module.cpp, задающий экспорты библиотек `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory` и `DllGetClassObject`.  
  
## См. также  
 [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)