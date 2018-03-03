---
title: "Шаблон проекта библиотеки классов WRL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13fc476f696bdd2cb17ed58c496c63747db90322
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-class-library-project-template"></a>Шаблон проекта библиотеки классов WRL
Если вы используете Visual Studio для записи проекта библиотеки шаблонов C++ (WRL) среды выполнения Windows, можно значительно упростить задачу, загрузив шаблон проекта библиотеки классов WRL.  
  
> [!NOTE]
>  Если необходимо вручную обновить параметры проекта для существующего проекта, см. раздел [библиотек DLL (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## <a name="download-the-wrl-project-template"></a>Загрузка шаблона проекта WRL  
 Visual Studio не предоставляет шаблон для проектов библиотека шаблонов C++ среды выполнения Windows. Вот как можно загрузить шаблон проекта, который создает базовую библиотеку классов для приложений универсальной платформы Windows с библиотека шаблонов C++ среды выполнения Windows.  
  
#### <a name="to-download-the-wrl-project-template"></a>Загрузка шаблона проекта WRL  
  
1.  В строке меню выберите **файл**, **новый проект**.  
  
2.  В левой области **новый проект** установите флажок **Online**, а затем выберите **шаблоны**.  
  
3.  В **найти шаблоны в Интернете** в верхнем правом углу типа `WRL Class Library`. Когда шаблон появится в результатах поиска, нажмите **ОК** кнопки.  
  
4.  В **загрузить и установить** выражений диалоговое окно, если вы согласны с лицензирования, выберите **установить** кнопки.  
  
5.  После установки шаблона создайте проект, выбрав **файл**, **новый проект**, а затем выбрав `WRLClassLibrary` шаблона. Проект создает библиотеку DLL.  
  
## <a name="examples-that-use-the-project-template"></a>Примеры, использующие шаблон проекта  
 Чтение [Пошаговое руководство: создание основного компонента среды выполнения Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) пример, который использует этот шаблон для создания компонента среды выполнения Windows.  
  
## <a name="what-the-project-template-provides"></a>Что содержит шаблон проекта  
 Шаблон проекта предоставляет:  
  
-   IDL-файл, который объявляет атрибуты MIDL для базового интерфейса реализации класса. Ниже приведен пример.  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   CPP-файл, в котором задана реализация класса. Ниже приведен пример.  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md) базовый класс помогает управлять глобальной ссылкой всех объектов модуля и объявляет методы [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332) и [IInspectable](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c) интерфейсов. [InspectableClass](../windows/inspectableclass-macro.md) реализует макрос `IUnknown` и `IInspectable`. [ActivatableClass](../windows/activatableclass-macros.md) макрос создает фабрику класса, который создает экземпляры класса.  
  
-   Файл с именем module.cpp, в котором определены функции экспорта библиотек `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory` и `DllGetClassObject`.  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)