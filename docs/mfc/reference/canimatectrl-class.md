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
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c4b8472a0dd8d2470f8e069e144efd0949201266
ms.lasthandoff: 04/01/2017

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
|[CAnimateCtrl::Close](#close)|Закрывает AVI-clip.|  
|[CAnimateCtrl::Create](#create)|Создает элемент управления анимации и прикрепляет его к `CAnimateCtrl` объекта.|  
|[CAnimateCtrl::CreateEx](#createex)|Создает элемент управления анимацию с указанного расширенные стили Windows и прикрепляет его к `CAnimateCtrl` объекта.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Указывает, воспроизводится ли клип чередуются аудио-видео (AVI).|  
|[CAnimateCtrl::Open](#open)|Открывает AVI-clip из файла или ресурса и отображает первый кадр.|  
|[CAnimateCtrl::Play](#play)|Воспроизведение ролика AVI без звука.|  
|[CAnimateCtrl::Seek](#seek)|Отображает выбранный один кадр ролика AVI.|  
|[CAnimateCtrl::Stop](#stop)|Останавливает воспроизведение AVI.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент управления (и, следовательно, `CAnimateCtrl` класс) доступен только для программ, работающих в Windows 95, Windows 98 и Windows NT версии 3.51 и более поздних.  
  
 Элемент управления анимации — прямоугольное окно, отображающий клип в формате AVI (звука видео с чередованием) — стандартный формат видео и аудио Windows. AVI-clip представляет собой ряд кадров растрового изображения, такие как фильма.  
  
 Элементы управления анимацией можно воспроизвести только простые ролики AVI. В частности клипы для воспроизведения, элемент управления анимации должна соответствовать следующим требованиям:  
  
-   Должно быть ровно один поток видео и должен иметь по крайней мере на один кадр.  
  
-   Может существовать не более двух потоков в файле (обычно потока, если он имеется, является аудиопоток, несмотря на то, что элемент управления анимации игнорирует звуковые сведения).  
  
-   Клип необходимо несжатых данных или с применением сжатия RLE8.  
  
-   Изменения палитры не разрешены в поток видео.  
  
 Можно добавить в приложение в качестве ресурса AVI AVI-clip или его можно дополнять приложения как отдельный файл AVI.  
  
 Так как поток продолжает выполнение во время отображения AVI-clip, часто используются для управления "анимация" — для указания активности системы во время продолжительной операции. Например поиск отображает диалоговое окно проводника скользящего увеличительное стекло как система выполняет поиск файла.  
  
 Если вы создаете `CAnimateCtrl` объекта в диалоговое окно, поле или из ресурса диалогового окна, с помощью редактора диалоговых окон, он будет автоматически уничтожен, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CAnimateCtrl` объекта в окне, может потребоваться удалить его. Если вы создаете `CAnimateCtrl` объекта в стеке, удаляется автоматически. При создании `CAnimateCtrl` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы удалить его. Если необходимо наследовать новый класс из `CAnimateCtrl` и выделять память в этом классе, переопределять `CAnimateCtrl` деструктор для удаления распределения.  
  
 Дополнительные сведения об использовании `CAnimateCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 Создает объект `CAnimateCtrl`.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [создать](#create) функция-член перед тем как выполнять другие операции для создания объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog #56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>CAnimateCtrl::Close  
 Закрывает клип AVI, который ранее был открыт в элементе управления "анимация" (если таковые имеются) и удаляет его из памяти.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>CAnimateCtrl::Create  
 Создает элемент управления анимации и прикрепляет его к `CAnimateCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления анимации. Примените любое сочетание описано стили, описанные в разделе «примечания» ниже и Стили анимации элемента управления в windows [Стили анимации элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761886) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает положение и размер элемента управления анимации. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления анимации, обычно `CDialog`. Он не должен быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор элемента управления анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CAnimateCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления, анимации и прикрепляет его к `CAnimateCtrl` объекта.  
  
 Применить следующие [стили окна](../../mfc/reference/window-styles.md) к элементу управления анимации.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 Если вы хотите использовать windows расширенных стилей с элементом управления анимации, вызовите [CreateEx](#createex) вместо **создать**.  
  
 Помимо стилей окна, перечисленных выше может потребоваться применить один или несколько стилей анимации элементов управления к элементу управления анимации. В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о [Стили анимации элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>CAnimateCtrl::CreateEx  
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
 Задает стиль элемента управления анимации. Примените любое сочетание окна и Стили анимации элемента управления, описанных в [Стили анимации элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761886) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Указывает, воспроизводится ли клип чередуются аудио-видео (AVI).  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если воспроизводится AVI-clip; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="open"></a>CAnimateCtrl::Open  
 Вызывайте эту функцию, чтобы открыть AVI-clip и отобразить его первый кадр.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Объект `CString` объекта или указателя символом null строку, которая содержит имя файла AVI либо имя ресурса AVI. Если этот параметр имеет **NULL**, система закрывает клип AVI, который ранее был открыт для управления "анимация", если таковые имеются.  
  
 `nID`  
 Идентификатор ресурса AVI. Если этот параметр имеет **NULL**, система закрывает клип AVI, который ранее был открыт для управления "анимация", если таковые имеются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Ресурс AVI загружается из модуля, который создан управления "анимация".  
  
 **Откройте** не поддерживает звук в AVI-clip; можно открыть только автоматической отсекает AVI.  
  
 Если для элемента управления анимации `ACS_AUTOPLAY` стиля, управления "анимация" будет автоматически начинать воспроизведение сразу после его открывает его. Она будет продолжать воспроизводить клип в фоновом режиме, пока поток продолжает выполнение. После завершения клип воспроизведение, он будет автоматически повторять.  
  
 Если для элемента управления анимации `ACS_CENTER` стиля, AVI-clip будет выравниваться по центру в элементе управления, а не меняет размер элемента управления. Если нет управления "анимация" `ACS_CENTER` стиля, элемент управления будет изменен при открытии AVI размер изображений в AVI-clip. Позиция верхнего левого угла элемента управления не изменится, только размер элемента управления.  
  
 Если для элемента управления анимации `ACS_TRANSPARENT` стиль, будет отображен первый кадр с прозрачным фоном, а не указан цвет фона в clip анимации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>CAnimateCtrl::Play  
 Эта функция вызывается для воспроизведения AVI-clip в элемент управления анимации.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Параметры  
 `nFrom`  
 Отсчитываемый от нуля индекс начала воспроизведения кадра. Значение должно быть меньше, чем 65 536 байт. Значение 0 означает начинаться с первого кадра в AVI-clip.  
  
 `nTo`  
 Отсчитываемый от нуля индекс кадра где воспроизведение завершается. Значение должно быть меньше, чем 65 536 байт. Значение - 1 означает заканчиваться последнего кадра ролика AVI.  
  
 *nRep*  
 Количество раз для воспроизведения AVI-clip. Значение - 1 означает неограниченное время воспроизведения в файл.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Управления "анимация" воспроизводится клип в фоновом режиме, пока поток продолжает выполнение. Если для элемента управления анимации `ACS_TRANSPARENT` стиля, AVI-clip будет воспроизводиться с помощью прозрачного фона, а не цвет фона, указанные в коллекции анимации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>CAnimateCtrl::Seek  
 Эта функция используется для отображения один кадр вашей AVI-clip статически.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Параметры  
 `nTo`  
 Отсчитываемый от нуля индекс фрейм для отображения. Значение должно быть меньше, чем 65 536 байт. Значение 0 означает отображение первый кадр ролика AVI. Значение -1 означает отображения последнего кадра ролика AVI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если для элемента управления анимации `ACS_TRANSPARENT` стиль, будет отображен AVI-clip с прозрачным фоном, а не указан цвет фона в clip анимации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>CAnimateCtrl::Stop  
 Вызывайте эту функцию, чтобы остановить воспроизведение AVI в элемент управления анимации.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)


