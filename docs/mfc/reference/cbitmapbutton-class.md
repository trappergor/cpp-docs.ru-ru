---
title: "Класс CBitmapButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- buttons, bitmap
- CBitmapButton class
- bitmaps, button controls
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 16d39cb380b75e6dcef71dda01626f120d5c12fb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmapbutton-class"></a>Класс CBitmapButton
Создает элементы управления "кнопка", на которые вместо текста помещаются растровые изображения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Создает объект `CBitmapButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|Связывает кнопки в диалоговом окне с объектом `CBitmapButton` загружает bitmap(s) по имени класса и размеров кнопки в соответствии с битовой карты.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Инициализирует объект, загрузка одного или нескольких ресурсов, именованных точечный рисунок из файла ресурсов приложения, подключив точечные рисунки объекта.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Размеры кнопки в соответствии точечного рисунка.|  
  
## <a name="remarks"></a>Примечания  
 `CBitmapButton`объекты содержат до четырех точечных рисунков, содержащих образы для различных состояний кнопки можно считать: вверх (или обычное), вниз (или выделенной), фокус и отключить. Только первый точечный рисунок является обязательным; остальные записи являются необязательными.  
  
 Кнопка с рисунком образы содержат границы вокруг изображения, а также само изображение. Границы обычно играет роль при отображении состояние кнопки. Например растровое изображение для конкретное состояние обычно является приведенный в актуальном состоянии, но с пунктирным прямоугольником отступ от границы или Толстая сплошная линия границы. Точечного рисунка для отключенного состояния обычно напоминающее для в актуальном состоянии, но имеет менее контрастных (например, Выбор меню недоступны или выделенный серым цветом).  
  
 Эти точечные рисунки могут быть любого размера, но все рассматриваются, как если бы они же размера, как растровое изображение для состояния системы.  
  
 Различные приложениям требуются различные сочетания растровых изображений:  
  
|Вверх|Вниз|Focused|Отключено|Приложение|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Кнопка без **WS_TABSTOP** стиля|  
|×|×|×|×|Кнопка диалогового окна с всех состояний|  
|×|×|×||Кнопка диалогового окна с **WS_TABSTOP** стиля|  
  
 При создании точечного рисунка кнопки задать **BS_OWNERDRAW** стиль, чтобы указать, что кнопки пользователем. В результате Windows для отправки `WM_MEASUREITEM` и `WM_DRAWITEM` сообщений для кнопки; framework обрабатывает эти сообщения и управляет внешний вид кнопки для вас.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Создание элемента управления, кнопка с рисунком в клиентской области окна  
  
1.  Создание четырех растровых изображений для кнопки.  
  
2.  Создать [CBitmapButton](#cbitmapbutton) объекта.  
  
3.  Вызов [создать](../../mfc/reference/cbutton-class.md#create) функция для создания элемента управления button Windows и присоединить его к `CBitmapButton` объекта.  
  
4.  Вызов [LoadBitmaps](#loadbitmaps) функции-члена для загрузки точечного рисунка ресурсов, после создания растрового изображения кнопки.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Чтобы включить элемент управления button точечного рисунка в диалоговом окне  
  
1.  Создание четырех растровых изображений для кнопки.  
  
2.  Создание шаблона диалоговое окно с кнопкой рисование владельцем располагается место кнопка с рисунком. Размер кнопки в шаблоне не имеет значения.  
  
3.  Задать название кнопки значение, например « **MYIMAGE**» и определить символ для кнопки, таких как **IDC_MYIMAGE**.  
  
4.  В скрипте ресурсов приложения предоставления каждому образы, созданные для кнопки идентификатор, созданный путем добавления одной из букв «U», «D», «F», или «X» (для вверх, вниз, фокус и отключить) строка, используемая для подписи кнопки в шаге 3. Для подписи кнопки» **MYIMAGE**, «идентификаторов может быть, например, « **MYIMAGEU**,»» **MYIMAGED**,»» **MYIMAGEF**,» и « **MYIMAGEX**.» Вы **необходимо** укажите идентификатор точечные рисунки в двойные кавычки. В противном случае редактор ресурсов будет назначить ресурс целое число и MFC произойдет сбой при загрузке образа.  
  
5.  В классе диалогового окна приложения (производный от `CDialog`), добавьте `CBitmapButton` объект члена.  
  
6.  В `CDialog` объекта [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) вызов процедуры, `CBitmapButton` объекта [автозагрузки](#autoload) функции используются в качестве параметров идентификатор элемента управления кнопки и `CDialog` объекта **это** указателя.  
  
 Следует ли обрабатывать сообщения уведомления Windows, таких как **BN_CLICKED**, отправленных на элементе управления кнопка с рисунком в родительском (обычно класс, производный от **CDialog)**, добавьте `CDialog`-производный объект схемы сообщений входа и обработчик сообщений функции-члена для каждого сообщения. Уведомления, отправляемые по `CBitmapButton` являются такими же, как отправленные [CButton](../../mfc/reference/cbutton-class.md) объекта.  
  
 Класс [CToolBar](../../mfc/reference/ctoolbar-class.md) использует другой подход к точечный рисунок кнопки.  
  
 Дополнительные сведения о `CBitmapButton`, в разделе [управления](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="autoload"></a>CBitmapButton::AutoLoad  
 Связывает кнопки в диалоговом окне с объектом `CBitmapButton` загружает bitmap(s) по имени класса и размеров кнопки в соответствии с битовой карты.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления кнопки.  
  
 `pParent`  
 Указатель на объект, которому принадлежит кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `AutoLoad` функцию для инициализации кнопка рисования владельцем в диалоговом окне кнопки точечного рисунка. Инструкции по использованию этой функции приведены в комментарии для `CBitmapButton` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#75;](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 Создает объект `CBitmapButton`.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Примечания  
 После создания C++ `CBitmapButton` , вызовите [CButton::Create](../../mfc/reference/cbutton-class.md#create) для создания элемента управления button Windows и присоединить его к `CBitmapButton` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#57;](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 Используйте эту функцию, если требуется загрузить точечных рисунков, определенной их идентификаторы или имена ресурсов, или если вы не можете использовать `AutoLoad` работать так, как, например, вы создаете точечный рисунок кнопки, которая не является частью диалоговое окно.  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszBitmapResource*  
 Указывает нулем строку, содержащую имя растрового изображения для кнопки точечный рисунок обычный или состояние «вверх». Обязательный.  
  
 *lpszBitmapResourceSel*  
 Указывает нулем строка, содержащая имя точечного рисунка для элемента, выбранного кнопка с рисунком или состояние «вниз». Может быть **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Указывает на нулем строку, содержащую имя растрового изображения для кнопки точечного рисунка с фокусом ввода состояния. Может быть **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Указывает нулем строка, содержащая имя точечного рисунка для отключенного состояния кнопки точечного рисунка. Может быть **NULL**.  
  
 *nIDBitmapResource*  
 Указывает идентификатор ресурса ресурса растрового изображения для кнопки точечный рисунок обычный или состояние «вверх». Обязательный.  
  
 *nIDBitmapResourceSel*  
 Указывает порядковый номер ресурса ресурса растрового изображения для элемента, выбранного кнопка с рисунком или состояние «вниз». Может быть равен 0.  
  
 *nIDBitmapResourceFocus*  
 Указывает идентификатор ресурса ресурса растрового изображения для кнопки точечный рисунок конкретное состояние. Может быть равен 0.  
  
 *nIDBitmapResourceDisabled*  
 Указывает идентификатор ресурса ресурса точечного рисунка для отключенного состояния кнопки точечного рисунка. Может быть равен 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#58;](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 Эта функция используется для изменения размеров точечного рисунка кнопку, чтобы размер точечного рисунка.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#59;](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLTEST](../../visual-cpp-samples.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


