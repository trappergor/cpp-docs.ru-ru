---
title: "CStockPropImpl Class | Microsoft Docs"
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
  - "CStockPropImpl"
  - "ATL::CStockPropImpl"
  - "ATL.CStockPropImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [ATL], свойства хранения"
  - "CStockPropImpl class"
  - "свойства хранения, элементы управления ATL"
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStockPropImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для поддержки значения стандартные свойства.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T,  
class InterfaceName,   
const IID* piid= &_ATL_IIDOF(InterfaceName),   
const GUID* plibid= &CComModule::m_libid,   
WORD wMajor= 1,  
WORD wMinor= 0,   
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE CStockPropImpl :  
public IDispatchImpl< InterfaceName, piid, plibid, wMajor,  
   wMinor, tihclass>  
```  
  
#### Параметры  
 `T`  
 Класс, реализующий элемент управления, производный от `CStockPropImpl`.  
  
 `InterfaceName`  
 Сдвоенный интерфейс, предоставляющими стандартные свойства.  
  
 `piid`  
 Указатель на идентификатор IID `InterfaceName`.  
  
 `plibid`  
 Указатель на идентификатор LIBID библиотеки типов, содержащие определения `InterfaceName`.  
  
 `wMajor`  
 Основной номер версии библиотеки типов.  Значение по умолчанию \- 1.  
  
 `wMinor`  
 Дополнительный номер версии библиотеки типов.  Значение по умолчанию \- 0.  
  
 `tihclass`  
 Класс, используемый для управления сведения о типе для `T`.  Значение по умолчанию — `CComTypeInfoHolder`.  
  
## Члены  
  
### Открытые методы  
  
|||  
|-|-|  
|[get\_Appearance](../Topic/CStockPropImpl::get_Appearance.md)|Вызывайте этот метод для получения стиль рисования используемый элементом управления, например, квартирой или выпуклая граница.|  
|[get\_AutoSize](../Topic/CStockPropImpl::get_AutoSize.md)|Вызовите этот метод, чтобы получить состояние пометить, указывающее, если элемент управления не может быть любым другим размером.|  
|[get\_BackColor](../Topic/CStockPropImpl::get_BackColor.md)|Вызывайте этот метод для получения цвет фона элемента управления.|  
|[get\_BackStyle](../Topic/CStockPropImpl::get_BackStyle.md)|Вызывайте этот метод для получения стиль фона элемента управления или прозрачного и непрозрачного.|  
|[get\_BorderColor](../Topic/CStockPropImpl::get_BorderColor.md)|Вызывайте этот метод для получения цвет границы элемента управления.|  
|[get\_BorderStyle](../Topic/CStockPropImpl::get_BorderStyle.md)|Вызывайте этот метод для получения стиль границы элемента управления.|  
|[get\_BorderVisible](../Topic/CStockPropImpl::get_BorderVisible.md)|Вызовите этот метод, чтобы получить состояние если пометить который указывает границу элемента управления видимым или нет.|  
|[get\_BorderWidth](../Topic/CStockPropImpl::get_BorderWidth.md)|Вызывайте этот метод для получения ширину \(в точках\) границы элемента управления.|  
|[get\_Caption](../Topic/CStockPropImpl::get_Caption.md)|Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.|  
|[get\_DrawMode](../Topic/CStockPropImpl::get_DrawMode.md)|Вызывайте этот метод для получения режима документа элемента управления, например, перо XOR или изменить цвета.|  
|[get\_DrawStyle](../Topic/CStockPropImpl::get_DrawStyle.md)|Вызывайте этот метод для получения стиль рисования элемента управления, например, сплошная, пунктирная, либо.|  
|[get\_DrawWidth](../Topic/CStockPropImpl::get_DrawWidth.md)|Вызывайте этот метод для получения ширину \(в точках\) используемый методами документа элемента управления.|  
|[get\_Enabled](../Topic/CStockPropImpl::get_Enabled.md)|Вызовите этот метод, чтобы получить состояние пометить, указывающее, является ли элемент управления включен.|  
|[get\_FillColor](../Topic/CStockPropImpl::get_FillColor.md)|Вызывайте этот метод для получения цвет заливки элемента управления.|  
|[get\_FillStyle](../Topic/CStockPropImpl::get_FillStyle.md)|Вызывайте этот метод для получения стиль заливки элемента управления, например сплошная, прозрачный или крест\- насидел.|  
|[get\_Font](../Topic/CStockPropImpl::get_Font.md)|Этот метод вызывается для получения указателя на свойства шрифта элемента управления.|  
|[get\_ForeColor](../Topic/CStockPropImpl::get_ForeColor.md)|Вызовите этот метод, чтобы получить основной цвет элемента управления.|  
|[get\_HWND](../Topic/CStockPropImpl::get_HWND.md)|Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления.|  
|[get\_MouseIcon](../Topic/CStockPropImpl::get_MouseIcon.md)|Вызовите этот метод, чтобы получить свойства изображения изображения \(значка, растрового изображения или метафайлов\) была недоступна, когда указатель мыши находится над элементом управления.|  
|[get\_MousePointer](../Topic/CStockPropImpl::get_MousePointer.md)|Вызовите этот метод, чтобы получить тип указателя мыши, отображаемый, когда указатель мыши находится над элементом управления, например стрелками крестом или часов.|  
|[get\_Picture](../Topic/CStockPropImpl::get_Picture.md)|Вызовите этот метод, чтобы получить указатель на свойства изображения изображения \(значка, растрового изображения или метафайлов\).|  
|[get\_ReadyState](../Topic/CStockPropImpl::get_ReadyState.md)|Вызовите этот метод, чтобы получить состояние элемента управления вместо этого например, загрузки и произвел загрузку.|  
|[get\_TabStop](../Topic/CStockPropImpl::get_TabStop.md)|Вызывайте этот метод для получения пометить, указывающее, если элемент управления позицию табуляции или нет.|  
|[get\_Text](../Topic/CStockPropImpl::get_Text.md)|Вызовите этот метод, чтобы получить текст, отображаемый с элементом управления.|  
|[get\_Valid](../Topic/CStockPropImpl::get_Valid.md)|Вызовите этот метод, чтобы получить состояние пометить, указывающее, если элемент управления является допустимым.|  
|[get\_Window](../Topic/CStockPropImpl::get_Window.md)|Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления.  [CStockPropImpl::get\_HWND](../Topic/CStockPropImpl::get_HWND.md), идентичный элементу.|  
|[put\_Appearance](../Topic/CStockPropImpl::put_Appearance.md)|Вызовите этот метод, чтобы задать стиль рисования используемый элементом управления, например, квартирой или выпуклая граница.|  
|[put\_AutoSize](../Topic/CStockPropImpl::put_AutoSize.md)|Вызовите этот метод, чтобы пометить установить значение, указывающее, если элемент управления не может быть любым другим размером.|  
|[put\_BackColor](../Topic/CStockPropImpl::put_BackColor.md)|Вызовите этот метод, чтобы задать цвет фона элемента управления.|  
|[put\_BackStyle](../Topic/CStockPropImpl::put_BackStyle.md)|Вызывайте этот метод для задания стиля фона элемента управления.|  
|[put\_BorderColor](../Topic/CStockPropImpl::put_BorderColor.md)|Вызовите этот метод, чтобы задать цвет границы элемента управления.|  
|[put\_BorderStyle](../Topic/CStockPropImpl::put_BorderStyle.md)|Вызовите этот метод, чтобы задать стиль границы элемента управления.|  
|[put\_BorderVisible](../Topic/CStockPropImpl::put_BorderVisible.md)|Вызовите этот метод, чтобы установить значение, указывающее, если пометить границы элемента управления отображается.|  
|[put\_BorderWidth](../Topic/CStockPropImpl::put_BorderWidth.md)|Вызовите этот метод, чтобы задать ширину границы элемента управления.|  
|[put\_Caption](../Topic/CStockPropImpl::put_Caption.md)|Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.|  
|[put\_DrawMode](../Topic/CStockPropImpl::put_DrawMode.md)|Вызовите этот метод, чтобы установить режим рисования элемента управления, например, перо XOR или изменить цвета.|  
|[put\_DrawStyle](../Topic/CStockPropImpl::put_DrawStyle.md)|Вызовите этот метод, чтобы задать стиль рисования элемента управления, например, сплошная, пунктирная, либо.|  
|[put\_DrawWidth](../Topic/CStockPropImpl::put_DrawWidth.md)|Вызовите этот метод, чтобы задать ширину \(в точках\) используемый методами документа элемента управления.|  
|[put\_Enabled](../Topic/CStockPropImpl::put_Enabled.md)|Вызовите этот метод, чтобы пометить, указывающее, является ли элемент управления включен.|  
|[put\_FillColor](../Topic/CStockPropImpl::put_FillColor.md)|Вызовите этот метод, чтобы установить цвет заливки элемента управления.|  
|[put\_FillStyle](../Topic/CStockPropImpl::put_FillStyle.md)|Вызовите этот метод, чтобы задать стиль заливки элемента управления, например сплошная, прозрачный или крест\- насидел.|  
|[put\_Font](../Topic/CStockPropImpl::put_Font.md)|Вызывайте этот метод для задания свойства шрифта элемента управления.|  
|[put\_ForeColor](../Topic/CStockPropImpl::put_ForeColor.md)|Вызовите этот метод, чтобы установить цвет элемента управления.|  
|[put\_HWND](../Topic/CStockPropImpl::put_HWND.md)|Этот метод вернет значение E\_FAIL.|  
|[put\_MouseIcon](../Topic/CStockPropImpl::put_MouseIcon.md)|Вызывайте этот метод для задания свойств изображения изображения \(значка, растрового изображения или метафайлов\), отображаемый, когда указатель мыши находится над элементом управления.|  
|[put\_MousePointer](../Topic/CStockPropImpl::put_MousePointer.md)|Вызывайте этот метод для задания типа указателя мыши, отображаемый, когда указатель мыши находится над элементом управления, например стрелками крестом или часов.|  
|[put\_Picture](../Topic/CStockPropImpl::put_Picture.md)|Вызывайте этот метод для задания свойств изображения изображения \(значка, растрового изображения или метафайлов\) для отображения.|  
|[put\_ReadyState](../Topic/CStockPropImpl::put_ReadyState.md)|Вызовите этот метод, чтобы установить состояние готовности элемента управления, например, загрузки и произвел загрузку.|  
|[put\_TabStop](../Topic/CStockPropImpl::put_TabStop.md)|Вызовите этот метод, чтобы установить значение, указывающее, если пометить элемент управления позицию табуляции или нет.|  
|[put\_Text](../Topic/CStockPropImpl::put_Text.md)|Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.|  
|[put\_Valid](../Topic/CStockPropImpl::put_Valid.md)|Вызовите этот метод, чтобы пометить, указывающее, если элемент управления является допустимым.|  
|[put\_Window](../Topic/CStockPropImpl::put_Window.md)|Этот метод вызывает [CStockPropImpl::put\_HWND](../Topic/CStockPropImpl::put_HWND.md), который возвращает E\_FAIL.|  
|[putref\_Font](../Topic/CStockPropImpl::putref_Font.md)|Вызывайте этот метод для задания свойства шрифта элемента управления со счетчиком ссылок.|  
|[putref\_MouseIcon](../Topic/CStockPropImpl::putref_MouseIcon.md)|Вызывайте этот метод для задания свойств изображения изображения \(значка, растрового изображения или метафайлов\), отображаемый, когда указатель мыши находится над элементом управления и счетчика ссылок.|  
|[putref\_Picture](../Topic/CStockPropImpl::putref_Picture.md)|Вызывайте этот метод для задания свойств изображения изображения \(значка, растрового изображения или метафайлов\), отображаемый с счетчиком ссылок.|  
  
## Заметки  
 `CStockPropImpl` предоставляет **обращен** и методы **get** для каждого стандартные свойства.  Эти методы предоставляют код, необходимый для размещения или получил элемент данных, который связан с каждым свойством и уведомления и синхронизировать с контейнером при изменении любого свойства.  
  
 Visual C\+\+ предоставляет поддержку для стандартных свойств через ее мастера.  Дополнительные сведения о добавлении стандартные свойства в элемент управления см. в разделе [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md).  
  
 Для обратной совместимости `CStockPropImpl` также предоставляет `get_Window` и методы `put_Window`, просто вызывает `get_HWND` и `put_HWND` соответственно.  Реализация по умолчанию `put_HWND` возвращает **E\_FAIL** поскольку `HWND` должен быть доступен только для чтения свойством.  
  
 Следующие свойства также имеют реализации **putref**:  
  
-   Шрифт  
  
-   MouseIcon  
  
-   Рисунок  
  
 3 Одинаковых стандартные свойства требуют их соответствующий элемент данных типа `CComPtr` или несколько другого класса, который обеспечивает правильную ссылку интерфейса, подсчитывая посредством оператора назначения.  
  
## Иерархия наследования  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)