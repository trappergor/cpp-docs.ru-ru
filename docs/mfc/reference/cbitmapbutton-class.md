---
title: Класс CBitmapButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef1c1a328b785c189a2d7d4a2eb28ec3995a810
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952184"
---
# <a name="cbitmapbutton-class"></a>Класс CBitmapButton
Создает элементы управления "кнопка", на которые вместо текста помещаются растровые изображения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Создает объект `CBitmapButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|Связывает кнопку в диалоговом окне с объектом `CBitmapButton` класса, загружает bitmap(s) по имени и размер кнопки в соответствии с растрового изображения.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Инициализирует объект, загрузка один или несколько ресурсов именованный точечный рисунок из файла ресурсов приложения, подключив точечные рисунки объекта.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Размеры кнопки в соответствии растрового изображения.|  
  
## <a name="remarks"></a>Примечания  
 `CBitmapButton` объект содержит до четырех точечные рисунки, содержащие изображения для различных состояний, можно предположить, кнопки: вверх (или обычный), вниз (или выделенной), с фокусом ввода, а также отключены. Только первый растровое изображение не требуется; другие являются необязательными.  
  
 Кнопка с рисунком образы содержать границы вокруг изображения, а также само изображение. Границы обычно играет роль при отображении состояние кнопки. Например растровое изображение для специальных состояния обычно используется как для актуальном состоянии, но с пунктирным прямоугольником отступ от границы или Толстая сплошная линия границы. Битовая карта для отключенного состояния обычно напоминает единицы для актуальном состоянии, но имеет менее контрастных (например, пункт меню серым цветом или выделена серым цветом).  
  
 Эти битовые карты могут быть любого размера, но все обрабатываются, как если бы они были совпадает с размером растровое изображение для состояния вверх.  
  
 Различные приложения требуются различные сочетания растровых изображений:  
  
|Вверх|Вниз|Focused|Отключено|Приложение|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Кнопка без **WS_TABSTOP** стиля|  
|×|×|×|×|Кнопка диалогового окна с всех состояний|  
|×|×|×||Кнопка диалогового окна с **WS_TABSTOP** стиля|  
  
 При создании элемента управления button растрового изображения, установите **BS_OWNERDRAW** стиль, чтобы указать, что кнопки владельцем. В результате Windows для отправки `WM_MEASUREITEM` и `WM_DRAWITEM` сообщений для кнопки; платформа обрабатывает эти сообщения и управляет внешний вид кнопки для вас.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Для создания растрового изображения кнопки в клиентской области окна  
  
1.  Создайте от одной до четырех растровые изображения для кнопки.  
  
2.  Создать [CBitmapButton](#cbitmapbutton) объекта.  
  
3.  Вызовите [создать](../../mfc/reference/cbutton-class.md#create) функции для создания элемента управления button Windows и присоединить его к `CBitmapButton` объекта.  
  
4.  Вызовите [LoadBitmaps](#loadbitmaps) функции-члена для загрузки ресурсов растрового изображения после создания растрового изображения кнопки.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Для включения точечного рисунка кнопке в диалоговом окне  
  
1.  Создайте от одной до четырех растровые изображения для кнопки.  
  
2.  Создание шаблона диалоговое окно с кнопкой рисуемый владельцем располагается место кнопки растрового изображения. Размер кнопки в шаблоне не имеет значения.  
  
3.  Задать значение кнопки например « **MYIMAGE**» и определить символ для кнопки, таких как **IDC_MYIMAGE**.  
  
4.  В сценарий ресурсов приложения предоставления каждому образы, созданные для кнопки, идентификатор, созданный путем добавления одной буквы «U», «D», «F», или «X» (для вверх, вниз, с фокусом ввода и отключен) строку, которая используется для подписи кнопки в шаге 3. Для подписи кнопки " **MYIMAGE**,» например, идентификаторы будет» **MYIMAGEU**,»» **MYIMAGED**,»» **MYIMAGEF**,» и « **MYIMAGEX**.» Вы **должен** укажите идентификатор точечные рисунки в двойные кавычки. В противном случае редактор ресурсов назначит целое ресурса и MFC произойдет сбой при загрузке образа.  
  
5.  В классе диалогового окна приложения (производный от `CDialog`), добавьте `CBitmapButton` объект члена.  
  
6.  В `CDialog` объекта [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) подпрограмме вызов `CBitmapButton` объекта [AutoLoad](#autoload) функции используются в качестве параметров идентификатор элемента управления кнопки и `CDialog` объекта **это** указателя.  
  
 Если требуется обрабатывать сообщения уведомления Windows, например BN_CLICKED, отправленных растрового изображения кнопки с родительским (обычно класс, производный от `CDialog`), добавьте `CDialog`-производного объекта члена входа и обработчик сообщений схемы сообщений функция для каждого сообщения. Уведомлений, отправляемых `CBitmapButton` объекта используются те же отправленных [CButton](../../mfc/reference/cbutton-class.md) объекта.  
  
 Класс [CToolBar](../../mfc/reference/ctoolbar-class.md) использует другой подход к кнопок с точечными рисунками.  
  
 Дополнительные сведения о `CBitmapButton`, в разделе [элементов управления](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="autoload"></a>  CBitmapButton::AutoLoad  
 Связывает кнопку в диалоговом окне с объектом `CBitmapButton` класса, загружает bitmap(s) по имени и размер кнопки в соответствии с растрового изображения.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления кнопки.  
  
 *pParent*  
 Указатель на объект, которому принадлежит кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `AutoLoad` функцию для инициализации рисуемый владельцем кнопка в диалоговом окне как кнопка растрового изображения. Инструкции по использованию данной функции находятся в комментарии для `CBitmapButton` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton  
 Создает объект `CBitmapButton`.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Примечания  
 После создания C++ `CBitmapButton` , вызовите [CButton::Create](../../mfc/reference/cbutton-class.md#create) для создания элемента управления button Windows и присоединить его к `CBitmapButton` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps  
 Используйте эту функцию, если вы хотите загрузить точечных рисунков, определенной их идентификаторы или имена ресурсов, или если вы не можете использовать `AutoLoad` работать так, как, например, вы создаете растрового изображения кнопки, которая не является частью диалоговое окно.  
  
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
 Указывает символом null строку, содержащую имя битовой карты для растрового изображения кнопки normal или состояние «вверх». Обязательно.  
  
 *lpszBitmapResourceSel*  
 Указывает символом null строку, которая содержит имя растрового изображения для кнопки растрового изображения выбранных или состояние «вниз». Возможно, **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Состояние указывает на символом null строку, содержащую имя растрового изображения для кнопки растрового изображения с фокусом ввода. Возможно, **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Указывает на символом null строку, содержащую имя растрового изображения для кнопки растрового изображения в отключенном состоянии. Возможно, **NULL**.  
  
 *nIDBitmapResource*  
 Указывает количество ресурсов идентификатор ресурса точечного рисунка для растрового изображения кнопки normal или состояние «вверх». Обязательно.  
  
 *nIDBitmapResourceSel*  
 Указывает количество ресурсов идентификатор ресурса точечного рисунка для выбранных кнопке растрового изображения или «вниз» состояние. Может быть равно 0.  
  
 *nIDBitmapResourceFocus*  
 Указывает количество ресурсов идентификатор ресурса точечного рисунка для специальных состояния растрового изображения кнопки. Может быть равно 0.  
  
 *nIDBitmapResourceDisabled*  
 Указывает количество ресурсов идентификатор ресурса точечного рисунка для кнопки растрового изображения при отключенном состоянии. Может быть равно 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent  
 Эта функция используется для изменения размеров точечного рисунка кнопку, чтобы размер растрового изображения.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLTEST](../../visual-cpp-samples.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

