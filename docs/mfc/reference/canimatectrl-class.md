---
title: "CAnimateCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [C++], CAnimateCtrl class
- Windows common controls [C++], CAnimateCtrl class
- CAnimateCtrl class
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cef1d6274d5334804ee028fa296c77faf124a496
ms.lasthandoff: 02/24/2017

---
# <a name="canimatectrl-class"></a>CAnimateCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления анимациями Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Создает объект `CAnimateCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|Закрывает ролика AVI.|  
|[CAnimateCtrl::Create](#create)|Создает элемент управления анимации и присоединяет его к `CAnimateCtrl` объекта.|  
|[CAnimateCtrl::CreateEx](#createex)|Создает элемент управления анимации с указанным расширенные стили Windows и присоединяет его к `CAnimateCtrl` объекта.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Указывает ли воспроизведения клипа чередуются аудио-видео (AVI).|  
|[CAnimateCtrl::Open](#open)|Открывает AVI клип из файла или ресурса и отображает первый кадр.|  
|[CAnimateCtrl::Play](#play)|Воспроизведение ролика AVI без звука.|  
|[CAnimateCtrl::Seek](#seek)|Отображает выбранный один кадр ролика AVI.|  
|[CAnimateCtrl::Stop](#stop)|Останавливает воспроизведение AVI.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент управления (и, следовательно, `CAnimateCtrl` класса) доступны только для программы, запущенные в Windows 95, Windows 98 и Windows NT версии 3.51 и более поздних версий.  
  
 Элемент управления анимации является прямоугольное окно, отображающее клипа в формате AVI (звука видео с чередованием) — стандартный формат аудио-Windows. AVI коллекции представляет собой ряд рамок точечного рисунка как фильм.  
  
 Элементы управления анимацией можно воспроизводить только простые ролики AVI. В частности воспроизведение элемента управления анимации клипов должен соответствовать следующим требованиям:  
  
-   Должно быть ровно один поток видео, и он должен иметь по крайней мере один кадр.  
  
-   Может существовать не более двух потоков в файле (обычно потока, если он присутствует, является аудиопоток, несмотря на то, что этот элемент управления игнорирует звуковой информации).  
  
-   Клип необходимо несжатых данных или с применением сжатия RLE8.  
  
-   Палитра изменения запрещены в поток видео.  
  
 Можно добавить в приложение в качестве ресурса AVI ролика AVI или он может сопровождать приложения как отдельный файл AVI.  
  
 Так как поток продолжает выполнение во время отображения ролика AVI, часто используются для управления анимации — указать активности системы во время продолжительной операции. Например диалоговое окно поиска проводника отображает перемещение увеличительное стекло как система выполняет поиск файла.  
  
 При создании `CAnimateCtrl` объекта в диалоговом поле или из ресурса диалогового окна, с помощью редактора диалоговых окон, оно автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CAnimateCtrl` объекта в окне, необходимо уничтожить его. При создании `CAnimateCtrl` объекта в стеке удаляется автоматически. При создании `CAnimateCtrl` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его. Если необходимо наследовать новый класс из `CAnimateCtrl` и выделять память в этом классе, переопределять `CAnimateCtrl` деструктор для удаления распределения.  
  
 Дополнительные сведения об использовании `CAnimateCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CAnimateCtrl с помощью](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namecanimatectrla--canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 Создает объект `CAnimateCtrl`.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [создать](#create) функция-член, перед выполнением других операций для создания объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#56;](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="a-nameclosea--canimatectrlclose"></a><a name="close"></a>CAnimateCtrl::Close  
 Закрывает ролика AVI, который ранее был открыт в элементе управления анимации (если есть) и удаляет его из памяти.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namecreatea--canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::Create  
 Создает элемент управления анимации и присоединяет его к `CAnimateCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления анимации. Примените любое сочетание windows, описано в разделе «примечания» ниже и стили элемента управления анимации стили описано в [стили элемента управления анимации](http://msdn.microsoft.com/library/windows/desktop/bb761886) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Указывает положение и размер элемента управления анимации. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления анимации, обычно `CDialog`. Оно не должно быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор элемента управления анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Создании `CAnimateCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает этот элемент управления и присоединяет его к `CAnimateCtrl` объекта.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) для элемента управления анимации.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 Если вы хотите использовать windows расширенных стилей с элементом управления анимации, вызвать [CreateEx](#createex) вместо **создать**.  
  
 Помимо стилей окна, перечисленных выше можно применить один или несколько стилей элемента управления анимации к элементу управления анимации. В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о [стили элемента управления анимации](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namecreateexa--canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CAnimateCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль элемента управления анимации. Примените любое сочетание окна и стили элемента управления анимации, описанных в [стили элемента управления анимации](http://msdn.microsoft.com/library/windows/desktop/bb761886) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-nameisplayinga--canimatectrlisplaying"></a><a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Указывает ли воспроизведения клипа чередуются аудио-видео (AVI).  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если воспроизводится клип AVI; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameopena--canimatectrlopen"></a><a name="open"></a>CAnimateCtrl::Open  
 Эта функция вызывается для ролика AVI открыть и отобразить его первый кадр.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Объект `CString` объект или указатель нулем строка, содержащая имя файла AVI либо имя ресурса AVI. Если этот параметр равен **NULL**, система закрывает клип AVI, который ранее был открыт для управления анимации, при их наличии.  
  
 `nID`  
 Идентификатор ресурса, AVI. Если этот параметр равен **NULL**, система закрывает клип AVI, который ранее был открыт для управления анимации, при их наличии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 AVI ресурс загружается из модуля, создавшего этот элемент управления.  
  
 **Откройте** не поддерживает звук ролика AVI; можно открыть только автоматическую ролика AVI.  
  
 Если у элемента управления анимации `ACS_AUTOPLAY` стиль, этот элемент управления будет автоматический запуск воспроизведения клипа сразу после его открывает его. Она будет продолжать воспроизводить клип в фоновом режиме, пока поток продолжает выполнение. После клипа воспроизведение, он будет автоматически повторяться.  
  
 Если у элемента управления анимации `ACS_CENTER` стиль, AVI клип будет выравниваться по центру в элементе управления, а не меняет размер элемента управления. Если этот элемент управления не имеет `ACS_CENTER` стиль, размер элемента управления будет изменен, при открытии AVI размер изображения ролика AVI. Положение верхнего левого угла элемента управления не изменится, размер элемента управления.  
  
 Если у элемента управления анимации `ACS_TRANSPARENT` стиль, будет отображен первый кадр с прозрачным фоном, а не указан цвет фона в другой клип.  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-nameplaya--canimatectrlplay"></a><a name="play"></a>CAnimateCtrl::Play  
 Эта функция вызывается для воспроизведения клипа AVI в элемент управления анимации.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Параметры  
 `nFrom`  
 Отсчитываемый от нуля индекс начала воспроизведения кадра. Значение должно быть меньше, чем 65 536 байт. Значение 0 означает начинается с первого кадра ролика AVI.  
  
 `nTo`  
 Отсчитываемый от нуля индекс кадра, где воспроизведение завершается. Значение должно быть меньше, чем 65 536 байт. Значение-1 означает заканчивается на последний кадр ролика AVI.  
  
 *nRep*  
 Количество раз для воспроизведения клипа AVI. Значение-1 означает неограниченное время воспроизведения файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Этот элемент управления будет воспроизводить клип в фоновом режиме, прерывая выполнение потока. Если у элемента управления анимации `ACS_TRANSPARENT` стиль, AVI клип будет воспроизводиться с помощью прозрачный фон, а не цвет фона, указанных в другой клип.  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-nameseeka--canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl::Seek  
 Эта функция вызывается для статически отображаться один кадр AVI-клипа.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Параметры  
 `nTo`  
 Отсчитываемый от нуля индекс фрейм для отображения. Значение должно быть меньше, чем 65 536 байт. Значение 0 означает отображение первый кадр ролика AVI. Значение -1 означает отображение последнего кадра ролика AVI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Если у элемента управления анимации `ACS_TRANSPARENT` стиль, будет отображен ролика AVI с прозрачным фоном, а не указан цвет фона в другой клип.  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namestopa--canimatectrlstop"></a><a name="stop"></a>CAnimateCtrl::Stop  
 Эта функция вызывается для остановки воспроизведения клипа AVI в элемент управления анимации.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
  В примере показано [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)


