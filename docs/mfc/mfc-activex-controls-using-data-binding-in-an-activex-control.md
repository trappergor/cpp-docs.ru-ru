---
title: "Элементы управления ActiveX MFC: Использование привязки данных в элементе управления ActiveX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e8416e7a176c00e5fb3067d1c1cfa447445dab54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>Элементы управления ActiveX в MFC. Использование привязки данных в элементе управления ActiveX
Одним из применений более мощных элементов управления ActiveX — привязки к данным, позволяющую свойства нужно привязать элемент управления с определенным полем в базе данных. Когда пользователь изменяет данные в этом связанное свойство, элемент управления уведомляет базы данных и обновить поле записи запросов. Базы данных уведомляет элемент управления об успехе или сбое запроса.  
  
 В этой статье рассматриваются управления части задачи. Реализация привязки данных взаимодействия с базой данных отвечает контейнера элемента управления. Как управлять взаимодействие с базой данных в контейнере выходит за рамки данной документации. В оставшейся части этой статьи объясняется способ подготовки элемента управления для привязки данных.  
  
 ![Концептуальная схема данных &#45; привязанного элемента управления](../mfc/media/vc374v1.gif "vc374v1")  
Концептуальная схема элемента управления с привязкой к данным  
  
 `COleControl` Класс предоставляет две функции-члены, предоставляющие простой процесс, для реализации привязки. Первая функция [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), будет использоваться для запроса разрешений, чтобы изменить значение свойства. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), вторая функция вызывается после успешного изменения значения свойства.  
  
 В этой статье рассматриваются следующие темы:  
  
-   [Создание стандартного привязываемые свойства](#vchowcreatingbindablestockproperty)  
  
-   [Создание метода привязываемых Get и Set.](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a>Создание стандартного привязываемые свойства  
 Имеется возможность создать стандартное свойство с привязкой к данным, несмотря на то, что скорее всего, будет необходимо [метод привязываемых get и set](#vchowcreatingbindablegetsetmethod).  
  
> [!NOTE]
>  Стандартные свойства имеют **привязываемых** и **requestedit** атрибуты по умолчанию.  
  
#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Чтобы добавить стандартное свойство привязки с помощью мастера добавления свойства  
  
1.  Начать проект с помощью [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md).  
  
2.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления.  
  
     Открывается контекстное меню.  
  
3.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить свойство**.  
  
4.  Выберите одну из записей из **имя свойства** раскрывающегося списка. Например, можно выбрать **текст**.  
  
     Поскольку **текст** стандартное свойство **привязываемых** и **requestedit** атрибуты уже проверены.  
  
5.  Установите следующие флажки из **атрибуты IDL** вкладка: **displaybind** и **defaultbind** добавить атрибуты к определению свойств в проекте. IDL-файл. Эти атрибуты сделать элемент управления видимым для пользователя и сделать стандартное свойство привязываемые свойства по умолчанию.  
  
 В этот момент элемент управления может отображать данные из источника данных, но пользователь не сможет обновить поля данных. Если необходимо также иметь возможность обновлять данные, измените элемент управления `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) функция выглядеть следующим образом:  
  
 [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
 Теперь можно построить проект, который будет зарегистрировать элемент управления. При вставке элемента управления в диалоговом окне, **поля данных** и **источника данных** будут добавлены свойства и теперь можно выбрать источник данных и поле для отображения в элементе управления.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a>Создание метода привязываемых Get и Set.  
 Помимо привязкой к данным метода get или set, можно также создавать [привязываемых стандартное свойство](#vchowcreatingbindablestockproperty).  
  
> [!NOTE]
>  Подразумевается, что у вас есть элемент управления ActiveX проекта который наследуется от класса элемента управления Windows Forms.  
  
#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Чтобы добавить метод привязываемых get и set, с помощью мастера добавления свойства  
  
1.  Загрузите проект элемента управления.  
  
2.  На **параметры управления** выберите класс окна элемента управления для подкласса. Например можно создать подкласс элемента управления.  
  
3.  Загрузите проект элемента управления.  
  
4.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления.  
  
     Открывается контекстное меню.  
  
5.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить свойство**.  
  
6.  Введите имя свойства в **имя свойства** поле. Используйте `MyProp` для этого примера.  
  
7.  Выберите тип данных из **тип свойства** раскрывающегося списка. Используйте **короткие** для этого примера.  
  
8.  В поле **Тип реализации**выберите **Методы Get/Set**.  
  
9. Установите следующие флажки на вкладке атрибуты IDL: **привязываемых**, **requestedit**, **displaybind**, и **defaultbind** для добавления атрибуты к определению свойств в проекте. IDL-файл. Эти атрибуты сделать элемент управления видимым для пользователя и сделать стандартное свойство привязываемые свойства по умолчанию.  
  
10. Нажмите кнопку **Готово**.  
  
11. Изменить текст `SetMyProp` функции, чтобы он содержал следующий код:  
  
     [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]  
  
12. Параметр, передаваемый `BoundPropertyChanged` и `BoundPropertyRequestEdit` функции является идентификатор dispid свойство, которое является параметром, передаваемая атрибуту id() для свойства. IDL-файл.  
  
13. Изменить [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) , поэтому он содержит следующий код:  
  
     [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
14. Изменить `OnDraw` функции, чтобы он содержал следующий код:  
  
     [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]  
  
15. В разделе открытый файл заголовка файла заголовка для класса элемента управления добавьте следующие определения переменных-членов (конструкторы):  
  
     [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]  
  
16. Сделать следующую строку в последней строке `DoPropExchange` функции:  
  
     [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]  
  
17. Изменить `OnResetState` функции, чтобы он содержал следующий код:  
  
     [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]  
  
18. Изменить `GetMyProp` функции, чтобы он содержал следующий код:  
  
     [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]  
  
 Теперь можно построить проект, который будет зарегистрировать элемент управления. При вставке элемента управления в диалоговом окне, **поля данных** и **источника данных** будут добавлены свойства и теперь можно выбрать источник данных и поле для отображения в элементе управления.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)   

