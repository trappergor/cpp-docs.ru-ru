---
title: "Добавление нового интерфейса в проект ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.interface
dev_langs: C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21aeda51a917bcb48b16ff8f9c2bc505adc18f1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Добавление нового интерфейса в проект ATL
При добавлении интерфейса для объекта или элемента управления создается усеченные функции для каждого метода этого интерфейса. В объект или элемент управления можно добавлять только те интерфейсы, которые в данный момент найдено в существующую библиотеку типов. Кроме того, необходимо реализовать класс, в котором можно добавить интерфейс [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) макрос или, если проект имеет атрибуты, он должен иметь `coclass` атрибута.  
  
 Можно добавить новый интерфейс для управления одним из двух способов: вручную или с помощью мастеров кода в представлении классов.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Чтобы добавить интерфейс для существующего объекта или элемента управления с помощью мастеров кода в представлении классов  
  
1.  В [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя класса элемента управления. Например полный доступ или составного элемента управления или другой класс элемента управления, реализующий макрос BEGIN_COM_MAP в своем файле заголовка.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **реализовать интерфейс**.  
  
3.  Выберите интерфейсы для реализации в [мастера реализации интерфейса](../../ide/implement-interface-wizard.md). Если интерфейс не существует в любой доступной библиотеке типов, затем необходимо добавить его вручную в IDL-файл.  
  
### <a name="to-add-a-new-interface-manually"></a>Чтобы добавить новый интерфейс вручную  
  
1.  Добавьте определение нового интерфейса в IDL-файл.  
  
2.  Создайте производный объект или элемент управления в интерфейсе.  
  
3.  Создайте новый [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) для интерфейса или, если проект имеет атрибуты, добавьте `coclass` атрибута.  
  
4.  Реализуйте методы интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

