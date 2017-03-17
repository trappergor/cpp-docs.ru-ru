---
title: "Класс CMFCDynamicLayout | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
dev_langs:
- C++
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
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
ms.openlocfilehash: 3066da5e1f874c2f0f2a2564b15582d7238c539b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdynamiclayout-class"></a>Класс CMFCDynamicLayout
Определяет порядок перемещения и изменения размеров элементов управления при изменении размеров окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Создает объект `CMFCDynamicLayout`.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDynamicLayout::AddItem](#additem)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|  
|[CMFCDynamicLayout::Adjust](#adjust)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|  
|[CMFCDynamicLayout::Create](#create)|Хранит и проверяет главное окно.|  
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Возвращает указатель на главное окно.|  
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Возвращает минимальный размер окна для макета.|  
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Извлекает прямоугольник для текущей клиентской области окна.|  
|[CMFCDynamicLayout::HasItem](#hasitem)|Проверяет, добавлялся ли дочерний элемент управления в динамический макет.|  
|[CMFCDynamicLayout::IsEmpty](#isempty)|Проверяет, что в динамический макет не добавлялись дочерние окна.|  
|[CMFCDynamicLayout::LoadResource](#loadresource)|Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.|  
|статические [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по горизонтали, когда пользователь изменяет размер окна ее размещения.|  
|статические [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по горизонтали, когда пользователь изменяет размер окна ее размещения.|  
|статические [CMFCDynamicLayout::MoveNone](#movenone)|Возвращает [MoveSettings](#movesettings_structure) значение, представляющее без перемещения вертикальной или горизонтальной для дочернего элемента управления.|  
|статические [CMFCDynamicLayout::MoveVertical](#movevertical)|Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по вертикали, когда пользователь изменяет размер окна ее размещения.|  
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Задает минимальный размер окна для макета.|  
|статические [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по горизонтали изменяется при изменении пользователем размера окна ее размещения.|  
|статические [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по горизонтали изменяется при изменении пользователем размера окна ее размещения.|  
|статические [CMFCDynamicLayout::SizeNone](#sizenone)|Возвращает [SizeSettings](#sizesettings_structure) значение, представляющее размер для дочернего элемента управления не изменяется.|  
|статические [CMFCDynamicLayout::SizeVertical](#sizevertical)|Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по вертикали изменяется при изменении пользователем размера окна ее размещения.|  
  
## <a name="nested-types"></a>Вложенные типы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура CMFCDynamicLayout::MoveSettings](#movesettings_structure)|Инкапсулирует данные перемещения для элементов управления в динамическом макете.|  
|[Структура CMFCDynamicLayout::SizeSettings](#sizesettings_structure)|Инкапсулирует данные об изменении размера элементов управления в динамическом макете.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxlayout.h  
  
##  <a name="additem"></a>CMFCDynamicLayout::AddItem  
 Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).  
  
```  
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

 
BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```  
  
### <a name="parameters"></a>Параметры  
 `hwnd`  
 Дескриптор добавляемого окна.  
  
 `nID`  
 Идентификатор добавляемого дочернего элемента управления.  
  
 `moveSettings`  
 Структура, описывающая перемещение элемента управления при изменении размера окна.  
  
 `sizeSettings`  
 Структура, описывающая изменение размера элемента управления при изменении размера окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент был успешно добавлен; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.  
  
##  <a name="adjust"></a>CMFCDynamicLayout::Adjust  
 Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).  
  
```  
void Adjust();
```  
  
### <a name="remarks"></a>Примечания  
 Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.  
  
##  <a name="create"></a>CMFCDynamicLayout::Create  
 Хранит и проверяет главное окно.  
  
```  
BOOL Create(CWnd* pHostWnd);
```  
  
### <a name="parameters"></a>Параметры  
 pHostWnd  
 Указатель на главное окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если создание прошло успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethostwnd"></a>CMFCDynamicLayout::GetHostWnd  
 Возвращает указатель на главное окно.  
  
```  
CWnd* GetHostWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на главное окно.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию положения всех дочерних элементов управления пересчитываются относительно этого окна.   
  
##  <a name="getminsize"></a>CMFCDynamicLayout::GetMinSize  
 Возвращает минимальный размер окна для макета.  
  
```  
CSize GetMinSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальный размер окна для макета.  
  
### <a name="remarks"></a>Примечания  
 Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.  
  
##  <a name="getwindowrect"></a>CMFCDynamicLayout::GetWindowRect  
 Извлекает прямоугольник для текущей клиентской области окна.  
  
```  
void GetHostWndRect(CRect& rect,);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 После возвращения функцией этот параметр содержит ограничивающий прямоугольник области макета. Это выходной параметр. Входное значение перезаписывается.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasitem"></a>CMFCDynamicLayout::HasItem  
 Проверяет, добавлялся ли дочерний элемент управления в динамический макет.  
  
```  
BOOL HasItem(HWND hwnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hwnd`  
 Дескриптор окна для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если макет уже содержит данный элемент; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isempty"></a>CMFCDynamicLayout::IsEmpty  
 Проверяет, что в динамический макет не добавлялись дочерние окна.  
  
```  
BOOL IsEmpty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если макет не содержит элементов; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="loadresource"></a>CMFCDynamicLayout::LoadResource  
 Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.  
  
```  
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);  
```  
  
### <a name="parameters"></a>Параметры  
 `pHostWnd`  
 Указатель на главное окно.  
  
 `lpResource`  
 Указатель на буфер, содержащий ресурс AFX_DIALOG_LAYOUT.  
  
 `dwSize`  
 Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс загружен и применен для главного окна; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="movehorizontal"></a>CMFCDynamicLayout::MoveHorizontal  
 Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по горизонтали, когда пользователь изменяет размер окна ее размещения.  
  
```  
static MoveSettings MoveHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nRatio`  
 Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [MoveSettings](#movesettings_structure) значение, которое инкапсулирует запрошенный переместить отношение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="movehorizontalandvertical"></a>CMFCDynamicLayout::MoveHorizontalAndVertical  
 Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по горизонтали, когда пользователь изменяет размер окна ее размещения.  
  
```  
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nXRatio`  
 Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.  
  
 `nYRatio`  
 Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [MoveSettings](#movesettings_structure) значение, которое инкапсулирует запрошенный переместить отношение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="movenone"></a>CMFCDynamicLayout::MoveNone  
 Возвращает [MoveSettings](#movesettings_structure) значение, представляющее без перемещения вертикальной или горизонтальной для дочернего элемента управления.  
  
```  
static MoveSettings MoveNone();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [MoveSettings](#movesettings_structure) значение, которое устраняет на месте, элемент управления, чтобы не перемещаются при изменении размеров окна хоста.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="movesettings_structure"></a>Структура CMFCDynamicLayout::MoveSettings  
 Инкапсулирует данные перемещения для элементов управления в динамическом макете.  
  
```  
struct CMFCDynamicLayout::MoveSettings;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс является вложенным в `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal
Проверяет, задано ли в данных перемещения ненулевое перемещение по горизонтали.  
  

```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по горизонтали.  

 ## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone
 Проверяет, что задано нулевое перемещение данных.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `MoveSettings` задает нулевое перемещение.  

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical
  Проверяет, задано ли в данных перемещения ненулевое перемещение по вертикали.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по вертикали.  

##  <a name="movevertical"></a>CMFCDynamicLayout::MoveVertical  
 Возвращает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления перемещается по вертикали, когда пользователь изменяет размер окна ее размещения.  
  
```  
static MoveSettings MoveVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nRatio`  
 Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [MoveSettings](#movesettings_structure) значение, которое инкапсулирует запрошенный переместить отношение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setminsize"></a>CMFCDynamicLayout::SetMinSize  
 Задает минимальный размер окна для макета.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Необходимый минимальный размер макета.  
  
### <a name="remarks"></a>Примечания  
 Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.  
  
##  <a name="sizehorizontal"></a>CMFCDynamicLayout::SizeHorizontal  
 Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по горизонтали изменяется при изменении пользователем размера окна ее размещения.  
  
```  
static SizeSettings SizeHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nRatio`  
 Определяет в процентах, насколько будет меняться размер дочернего элемента управления по горизонтали при изменении размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует отношение требуемого размера.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizehorizontalandvertical"></a>CMFCDynamicLayout::SizeHorizontalAndVertical  
 Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по горизонтали изменяется при изменении пользователем размера окна ее размещения.  
  
```  
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nXRatio`  
 Определяет в процентах, насколько будет меняться размер дочернего элемента управления по горизонтали при изменении размера главного окна.  
  
 `nYRatio`  
 Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует отношение требуемого размера.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizenone"></a>CMFCDynamicLayout::SizeNone  
 Возвращает [SizeSettings](#sizesettings_structure) значение, представляющее размер для дочернего элемента управления не изменяется.  
  
```  
static SizeSettings SizeNone();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SizeSettings](#sizesettings_structure) значение, которое устраняет управления на определенный размер, таким образом, не меняя размер при изменении размеров окна хоста.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizesettings_structure"></a>Структура CMFCDynamicLayout::SizeSettings  
 Инкапсулирует данные об изменении размера элементов управления в динамическом макете.  
  
```  
struct CMFCDynamicLayout::SizeSettings;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс является вложенным в `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal
Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по горизонтали.  
  
```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по горизонтали. 

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone
Проверяет, задано ли в данных об изменении размера нулевое изменение размера.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `SizeSettings` задает нулевое изменение размера.  

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical
Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по вертикали.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по вертикали.  

##  <a name="sizevertical"></a>CMFCDynamicLayout::SizeVertical  
 Возвращает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления по вертикали изменяется при изменении пользователем размера окна ее размещения.  
  
```  
static SizeSettings SizeVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Параметры  
 `nRatio`  
 Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует отношение требуемого размера.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

