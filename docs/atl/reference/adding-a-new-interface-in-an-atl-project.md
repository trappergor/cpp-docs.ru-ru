---
title: "Добавление нового интерфейса в проект ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8e4916c60310dd8dcbf0bb9e8c1f151309a32621
ms.lasthandoff: 02/24/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Добавление нового интерфейса в проект ATL
При добавлении интерфейса в объект или элемент управления создается усеченные функции для каждого метода этого интерфейса. В объект или элемент управления можно добавить только интерфейсы, найденных в существующую библиотеку типов. Кроме того, необходимо реализовать класс, в который добавляется интерфейс [BEGIN_COM_MAP](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333) макрос или, если проект имеет атрибуты, он должен иметь `coclass` атрибута.  
  
 Новый интерфейс можно добавить в элемент управления двумя способами: вручную или с помощью мастеров кода в представлении классов.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Чтобы добавить интерфейс для существующего объекта или элемента управления с помощью мастеров кода в представлении классов  
  
1.  В [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя класса элемента управления. Например полный доступ или составной элемент управления или другой класс элемента управления, реализующий макрос BEGIN_COM_MAP в своем файле заголовка.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **реализовать интерфейс**.  
  
3.  Выберите интерфейсы для реализации в [мастера реализации интерфейса](../../ide/implement-interface-wizard.md). Если интерфейс не существует в любой доступной библиотеке типов, то необходимо добавить его вручную в IDL-файл.  
  
### <a name="to-add-a-new-interface-manually"></a>Добавление нового интерфейса вручную  
  
1.  Добавьте определение нового интерфейса в IDL-файл.  
  
2.  Унаследуйте нужный объект или элемент управления из интерфейса.  
  
3.  Создайте новый [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) для интерфейса или, если проект имеет атрибуты, добавьте `coclass` атрибута.  
  
4.  Реализуйте методы интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Мастер проекта ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для настольных ПК с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Конфигурации проекта ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)


