---
title: 'Контейнеры элементов ActiveX: Программирование элементов управления ActiveX в контейнере элементов управления ActiveX | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f68e74c5374379019fd8fd5b0348b34e36005171
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535331"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>Контейнеры элементов управления ActiveX. Программирование элементов управления ActiveX в контейнере элементов управления ActiveX
В этой статье описывается процесс для доступа к предоставляемым [методы](../mfc/mfc-activex-controls-methods.md) и [свойства](../mfc/mfc-activex-controls-properties.md) внедренных элементов управления ActiveX. 

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, которые следуют за ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

По сути выполняются следующие действия.  
  
1.  [Вставка элемента управления ActiveX в контейнере проекта ActiveX](../mfc/inserting-a-control-into-a-control-container-application.md) с помощью коллекции.  
  
2.  [Определение переменной-члена](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (или других видов доступа) того же типа как ActiveX класс оболочки элемента управления.  
  
3.  [Программирование элемента управления ActiveX](#_core_programming_the_activex_control) использовать предопределенные функции-члены класса-оболочки.  
  
 В этой статье предполагается, что вы создали проект на базе диалогового окна (с именем контейнера) с поддержкой элементов управления ActiveX. Элемент образца Кр Кр, будут добавляться в итоговый проект.  
  
 После вставки элемента управления Кр в проект (шаг 1) вставьте экземпляра элемента управления Кр в главное диалоговое окно приложения.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Добавление элемента управления Кр шаблона диалогового окна  
  
1.  Загрузите проект контейнера элемента управления ActiveX. В этом примере используйте `Container` проекта.  
  
2.  Перейдите на вкладку представления ресурсов.  
  
3.  Откройте **диалоговое окно** папки.  
  
4.  Дважды щелкните шаблон главного диалогового окна. В этом примере используйте **IDD_CONTAINER_DIALOG**.  
  
5.  Щелкните значок элемента управления Кр на панели элементов.  
  
6.  Щелкните место в диалоговом окне, чтобы вставить элемент управления Кр.  
  
7.  Из **файл** меню, выберите **сохранить все** сохранить все изменения в шаблон диалогового окна.  
  
## <a name="modifications-to-the-project"></a>Изменения в проект  
 Чтобы включить приложение-контейнер для доступа к элементу управления Кр, Visual C++ автоматически добавляет класс-оболочку (`CCirc`) файла реализации (. CPP) для проекта контейнера и заголовок класса программы-оболочки (. H) файл в файл заголовка для диалогового окна поле:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> Заголовок класса программы-оболочки (. H) файл  
 Для получения и задания свойств (и вызывать методы) для элемента управления Кр `CCirc` класс-оболочка содержит объявление, все они доступны методы и свойства. В примере эти объявления находятся в круглый З. Следующий пример является частью класса `CCirc` , определяющий интерфейсов элемента управления ActiveX:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 Затем, эти функции могут вызываться из других процедур приложения с помощью обычного синтаксиса C++. Дополнительные сведения об использовании этой функции-члена присвоено к методам и свойствам элемента управления, см. в разделе [программирование элемента управления ActiveX](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> Член переменной изменения в проект  
 Когда элемент управления ActiveX будет добавлена в проект и внедренных в контейнере поле диалоговых окон, он может осуществляться в других частях проекта. Самый простой способ доступа к элементу управления — [создать переменную-член](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) класс диалогового окна, `CContainerDlg` (шаг 2), то есть того же типа как класс-оболочка, добавленные в проект Visual C++. Затем можно использовать переменную-член для доступа к внедренного элемента управления в любое время.  
  
 Когда **добавления переменной-члена** диалоговое окно добавляет *m_circctl* член переменной в проект, он также добавляет следующие строки в файл заголовка (. H) из `CContainerDlg` класса:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 Кроме того, вызов **DDX_Control** автоматически добавляется `CContainerDlg`в реализации `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> Программирование элемента управления ActiveX  
 На этом этапе вы вставлено в шаблон диалогового окна элемент управления ActiveX и создали переменную-член для него. Общий синтаксис C++ теперь можно использовать для доступа к свойствам и методам внедренного элемента управления.  
  
 Как было отмечено (в [заголовок класса программы-оболочки (. H) файл](#_core_the_wrapper_class_header_28h29_file)), файл заголовка (. H) для `CCirc` класс-оболочку, в этом вариантов круглый H, содержит список функций-членов, которые можно использовать для получения и задания значения любого открытого свойства. Также доступны функции-члены для предоставленные методы.  
  
 Чаще всего для изменения свойств элемента управления находится в `OnInitDialog` функцию-член в класс диалогового окна. Эта функция вызывается непосредственно перед диалоговое окно появляется и используется для инициализации ее содержимое, включая его элементов управления.  
  
 В следующем примере кода используется *m_circctl* изменить заголовок и CircleShape свойства внедренного элемента управления Кр переменную-член:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

