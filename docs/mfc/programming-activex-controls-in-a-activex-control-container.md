---
title: "Контейнеры элементов управления ActiveX: Программирование элементов управления ActiveX в контейнере элементов управления ActiveX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b159e41a27254f44d9a9868012237875cc24d4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>Контейнеры элементов управления ActiveX. Программирование элементов управления ActiveX в контейнере элементов управления ActiveX
В этой статье описан процесс для доступа к предоставляемым [методы](../mfc/mfc-activex-controls-methods.md) и [свойства](../mfc/mfc-activex-controls-properties.md) внедренных элементов управления ActiveX. По сути выполняются следующие действия.  
  
1.  [Вставка элемента управления ActiveX в контейнере проекта ActiveX](../mfc/inserting-a-control-into-a-control-container-application.md) с помощью коллекции.  
  
2.  [Определение переменной-члена](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (или другие виды доступа) того же типа, как ActiveX класса программы-оболочки элемента управления.  
  
3.  [Программирование элемента управления ActiveX](#_core_programming_the_activex_control) с помощью заранее определенных функций-членов класса-оболочки.  
  
 В данном разделе предполагается, что вы создали проект на базе диалогового окна (с именем контейнера) с поддержкой элементов управления ActiveX. Элемент управления Circ образец Circ, будут добавлены в итоговый проект.  
  
 После управления Circ вставляется в проект (шаг 1), вставьте экземпляр элемента управления Circ в главном диалоговом приложения.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Чтобы добавить элемент управления Circ для шаблона диалогового окна  
  
1.  Загрузите проект контейнера элемента управления ActiveX. В этом примере используется `Container` проекта.  
  
2.  Перейдите на вкладку представления ресурсов.  
  
3.  Откройте **диалоговое окно** папки.  
  
4.  Дважды щелкните шаблон главного диалогового окна. В этом примере используется **IDD_CONTAINER_DIALOG**.  
  
5.  Щелкните значок элемента управления Circ на панели инструментов.  
  
6.  Щелкните место в диалоговом окне, чтобы вставить элемент управления Circ.  
  
7.  Из **файл** меню, выберите **сохранить все** сохранить все изменения в шаблон диалогового окна.  
  
## <a name="modifications-to-the-project"></a>Изменения в проект  
 Чтобы включить приложение-контейнер для доступа к элементу управления Circ, Visual C++ автоматически добавит класс-оболочку (`CCirc`) файла реализации (. CPP) в проект контейнера и заголовок класса программы-оболочки (. H) файла в диалоговом окне поле заголовка:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a>Заголовок класса программы-оболочки (. (H) файл  
 Для получения и задания свойств (и вызывать методы) для элемента управления Circ `CCirc` класс-оболочка обеспечивает объявление все они доступны методы и свойства. В примере эти объявления находятся в круглый З. Следующий пример является частью класса `CCirc` , определяющий интерфейсов элемента управления ActiveX:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 Затем, эти функции могут вызываться из других процедур приложения, с помощью обычного синтаксиса C++. Дополнительные сведения об использовании этой функции-члена присвоено к методам и свойствам элемента управления, обратитесь к разделу [программирование элемента управления ActiveX](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a>Член переменной изменения в проект  
 Когда элемент управления ActiveX был добавлен в проект и внедренных в контейнере поле диалоговых окон, доступны в других частях проекта. Самый простой способ доступа к элементу управления — [создать переменную-член](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) класс диалогового окна `CContainerDlg` (шаг 2), то есть того же типа, как класс-оболочку, добавленные в проект Visual C++. Затем можно использовать переменную-член для доступа к внедренный элемент управления в любое время.  
  
 Когда **добавления переменной-члена** диалоговое окно добавляет `m_circctl` член переменной в проект, а также добавляет следующие строки в файле заголовка (. H) из `CContainerDlg` класса:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 Кроме того, вызов **DDX_Control** автоматически добавляется в `CContainerDlg`реализация `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a>Программирование элемента управления ActiveX  
 На этом этапе вставлено в шаблон диалогового окна элемента управления ActiveX и создать переменную-член для нее. Общий синтаксис C++ теперь можно использовать для доступа к свойствам и методам внедренного элемента управления.  
  
 Как уже отмечалось (в [заголовок класса программы-оболочки (. H) файл](#_core_the_wrapper_class_header_28h29_file)), файл заголовка (. (H) для `CCirc` класс-оболочку, в этом вариантов круглый Символ «H» содержит список функций элементов, которые можно использовать для получения и задания любое значение открытого свойства. Также доступны функции-члены для предоставленные методы.  
  
 Единый механизм для изменения свойств элемента управления находится в `OnInitDialog` функции-члена класса главного диалогового окна. Эта функция вызывается непосредственно перед диалоговое окно появляется и используется для инициализации ее содержимое, включая его элементов управления.  
  
 Следующий пример кода использует `m_circctl` переменной-члена для изменения свойств элемента управления внедренных Circ заголовок и CircleShape:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

