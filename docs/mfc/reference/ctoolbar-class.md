---
title: "CToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "растровые изображения [C++], button controls"
  - "кнопки [C++], MFC toolbars"
  - "control bars [C++], CToolBar class"
  - "CToolBar class"
  - "панели инструментов [C++], CToolBar class"
  - "Windows common controls [C++], CToolBar class"
  - "Windows toolbar common controls [C++]"
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Панель элементов управления, имеющих строку bitmapped кнопок и разделителей необязательно.  
  
## Синтаксис  
  
```  
class CToolBar : public CControlBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CToolBar::CToolBar](../Topic/CToolBar::CToolBar.md)|Создает объект `CToolBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CToolBar::CommandToIndex](../Topic/CToolBar::CommandToIndex.md)|Возвращает индекс кнопки с заданным идентификатором команды|  
|[CToolBar::Create](../Topic/CToolBar::Create.md)|Создает панель инструментов Windows и вложение его к объекту `CToolBar`.|  
|[CToolBar::CreateEx](../Topic/CToolBar::CreateEx.md)|Создает объект `CToolBar` с помощью дополнительных стилей для внедренного объекта `CToolBarCtrl`.|  
|[CToolBar::GetButtonInfo](../Topic/CToolBar::GetButtonInfo.md)|Извлекает идентификатор, стиль и номер образа кнопки.|  
|[CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md)|Извлекает стиль кнопки.|  
|[CToolBar::GetButtonText](../Topic/CToolBar::GetButtonText.md)|Извлекает текст, который будет отображаться на кнопку.|  
|[CToolBar::GetItemID](../Topic/CToolBar::GetItemID.md)|Возвращает идентификатор команды кнопки или разделителя по заданному индексу.|  
|[CToolBar::GetItemRect](../Topic/CToolBar::GetItemRect.md)|Возвращает прямоугольник для элемента по указанному индексу.|  
|[CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)|Обеспечивает прямой доступ к общему элементу управления.|  
|[CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)|Загружает растровое изображение, содержащий растровое изображение\- изображений кнопок.|  
|[CToolBar::LoadToolBar](../Topic/CToolBar::LoadToolBar.md)|Загружает созданный ресурс панели инструментов с редактором ресурсов.|  
|[CToolBar::SetBitmap](../Topic/CToolBar::SetBitmap.md)|Задает bitmapped образа.|  
|[CToolBar::SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)|Устанавливает идентификатор, стиль и номер образа кнопки.|  
|[CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)|Наборы застегивают стили и индекс изображений кнопок в растровое изображение.|  
|[CToolBar::SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md)|Задает стиль кнопки.|  
|[CToolBar::SetButtonText](../Topic/CToolBar::SetButtonText.md)|Задает текст, который будет отображаться на кнопку.|  
|[CToolBar::SetHeight](../Topic/CToolBar::SetHeight.md)|Задает высоту панели инструментов.|  
|[CToolBar::SetSizes](../Topic/CToolBar::SetSizes.md)|Устанавливает размеры кнопок и их растровых изображений.|  
  
## Заметки  
 Кнопки могут действовать как кнопки, кнопки "флажок" или переключатели.  Объекты `CToolBar` обычно внедренные элементы объектов фреймового окна, производных от класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md), функция\-член новый с MFC 4.0 позволяет воспользоваться преимуществами поддержки управления Windows общим для настройки панели инструментов и дополнительными функциональными возможностями.  Функции\-члены необходимо `CToolBar` дают большую часть возможностей управления Windows общих; однако при вызове `GetToolBarCtrl`, можно предоставить пользовательским панель инструментов, даже несколько характеристик Windows 95 \/98 панелей инструментов.  При вызове `GetToolBarCtrl`, он возвращает ссылку на объект `CToolBarCtrl`.  См. раздел [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) дополнительные сведения о конструировании панели инструментов с помощью управления Windows общие.  Общие сведения о стандартных элементах управления см. в разделе [общие элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Visual C\+\+ предусмотрено 2 методами, чтобы создать панель инструментов.  Создание ресурса панели инструментов с помощью редактора ресурсов, выполните следующие действия:  
  
1.  Создание ресурса панели инструментов.  
  
2.  Создайте объект `CToolBar`.  
  
3.  Вызовите функцию [Создание](../Topic/CToolBar::Create.md) \(или [CreateEx](../Topic/CToolBar::CreateEx.md)\), чтобы создать панель инструментов Windows и вложить его к объекту `CToolBar`.  
  
4.  Вызов [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) для загрузки ресурса панели инструментов.  
  
 В противном случае, выполните следующие шаги:  
  
1.  Создайте объект `CToolBar`.  
  
2.  Вызовите функцию [Создание](../Topic/CToolBar::Create.md) \(или [CreateEx](../Topic/CToolBar::CreateEx.md)\), чтобы создать панель инструментов Windows и вложить его к объекту `CToolBar`.  
  
3.  Вызовите [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) для загрузки растровое изображение, содержащее изображений кнопок панели инструментов.  
  
4.  Вызовите [SetButtons](../Topic/CToolBar::SetButtons.md) для задания стиля кнопки и связать каждую кнопку с образом в растровом изображении.  
  
 Все изображений кнопок на панели инструментов берутся из одного растрового изображения, которое должно содержать один способ для каждой кнопки.  Все образы должны быть одинаковым размером; значение по умолчанию \- 16 пикселей по ширине и 15 пикселей высокого уровня.  Образы должны параллельно в растровом изображении.  
  
 Функция `SetButtons` принимает указатель на массив идентификаторов элементов управления и целое число, определяющее количество элементов в массиве.  Функция задает идентификатор каждой кнопки со значением соответствующего элемента массива и присвоит каждой кнопке индекс образа, который определяет положение изображения кнопок в растровом изображении.  Если элемент массива имеет значение **ID\_SEPARATOR**, индекс образа не присвоено.  
  
 Порядок изображений в растровом изображении обычно порядок, в котором они нарисована на экране, но можно использовать функцию [SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md) для изменения связи между заказом образа и порядком вывода.  
  
 Все кнопки на панели инструментов имеют одинаковый размер.  Значение по умолчанию \- 24 x 22 точки, в соответствии с *рекомендациям интерфейса Windows* for software design.  Любое дополнительное пространство между образ и измерения кнопки используется для формирования границу вокруг изображения.  
  
 Каждая кнопка имеет один способ.  Различные состояния и стили \(нажатые кнопки вверх, вниз, заблокированных, заблокированных, вниз и непредвиденный\) формируются из одного образа.  Хотя растровые изображения могут быть любые цветом, можно достигнуть лучших результатов с образами черным цветом и затенениях серого.  
  
> [!WARNING]
>  `CToolBar` поддерживает растровые изображения с максимальным значением 16.  При загрузке способ редактор панелей инструментов, Visual Studio автоматически преобразует образ в растровое изображение 16 цветов, если необходимый и отображает предупреждение, если образ был преобразован.  При использовании образ с более 16 цветов \(использование внешнего редактор для редактирования образ\), то приложение может повести себя, как ожидается.  
  
 Кнопки панели инструментов имитируют по умолчанию кнопок.  Однако кнопки панели инструментов также могут имитировать кнопки или переключатели флажка.  Флажок кнопки имеют 3 состояний: проверяемый, очищенный и непредвиденный.  Переключатели 2 имеют только состояния: проверяемый и очищенный.  
  
 Задать отдельный стиль кнопки или разделителя без указывать на массив, вызов [GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) для получения стиль, а затем вызвать [SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md) вместо `SetButtons`.  `SetButtonStyle` наиболее полезен, когда нужно изменить стиль кнопки во время выполнения.  
  
 Присвоение текста, чтобы появиться на кнопку вызвать [GetButtonText](../Topic/CToolBar::GetButtonText.md) для получения текста для отображения на кнопку, и затем вызывать [SetButtonText](../Topic/CToolBar::SetButtonText.md) для задания текста.  
  
 Для создания кнопки флажка, присвойте ей стиль **TBBS\_CHECKBOX** или используйте функции\-члена `SetCheck` объекта `CCmdUI` в обработчике `ON_UPDATE_COMMAND_UI`.  Вызов `SetCheck` включает кнопку в кнопку.  Передайте `SetCheck` аргумент равен 0, непроверенного, 1 или 2 для установленного флажка для неопределенного.  
  
 Для создания переключатель, вызовите функцию\-член [SetRadio](../Topic/CCmdUI::SetRadio.md) объекта [CCmdUI](../Topic/CCmdUI%20Class.md) из обработчика `ON_UPDATE_COMMAND_UI`.  Передайте `SetRadio` аргумент равен 0, непроверенного или ненулевого для установленного флажка.  Предоставить группу радио взаимно исключающая \- функциональности, необходимо иметь обработчики `ON_UPDATE_COMMAND_UI` для всех кнопок в группе.  
  
 Дополнительные сведения об использовании `CToolBar` см. в статье [реализация панели инструментов MFC](../../mfc/mfc-toolbar-implementation.md) и [Техническая примечание 31. Панель элементов управления](../../mfc/tn031-control-bars.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [MFC просматривает CTRLBARS](../../top/visual-cpp-samples.md)   
 [Образец DLGCBR32 MFC](../../top/visual-cpp-samples.md)   
 [Образец DOCKTOOL MFC](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CToolBar::Create](../Topic/CToolBar::Create.md)   
 [CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)   
 [CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)   
 [CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)   
 [CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)