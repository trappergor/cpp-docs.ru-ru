---
title: Добавление нового интерфейса в проект ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 057e70faf22a2e0cabe20bbcc80c18301011291c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956613"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Добавление нового интерфейса в проект ATL
При добавлении интерфейс для объекта или элемента управления, создаваемые усеченные функции для каждого метода в этот интерфейс. В объект или элемент управления можно добавить только интерфейсы, найденных в существующую библиотеку типов. Кроме того, необходимо реализовать класс, в котором добавляется интерфейс [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) макрос или, если проект имеет атрибуты, он должен иметь `coclass` атрибута.  
  
 Новый интерфейс можно добавить в элемент управления в одном из двух способов: вручную или с помощью мастеров кода в представлении классов.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Чтобы добавить интерфейс для существующего объекта или элемента управления с помощью мастеров кода в представлении классов  
  
1.  В [представление классов](/visualstudio/ide/viewing-the-structure-of-code), щелкните правой кнопкой мыши имя класса элемента управления. Например полный доступ или составного элемента управления или другой класс элемента управления, реализующий макрос BEGIN_COM_MAP в своем файле заголовка.  
  
2.  В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **реализовать интерфейс**.  
  
3.  Выберите интерфейсы для реализации в [мастера реализации интерфейса](../../ide/implement-interface-wizard.md). Если интерфейс не существует в любой доступной библиотеке типов, то необходимо добавить его вручную в IDL-файл.  
  
### <a name="to-add-a-new-interface-manually"></a>Чтобы вручную добавить новый интерфейс  
  
1.  Добавьте определение нового интерфейса в IDL-файл.  
  
2.  Наследовать объект или элемент управления с помощью интерфейса.  
  
3.  Создайте новый [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) для интерфейса или, если проект имеет атрибуты, добавьте `coclass` атрибута.  
  
4.  Реализуйте методы в интерфейсе.  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

