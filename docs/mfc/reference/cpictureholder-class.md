---
title: "Класс CPictureHolder | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
dev_langs:
- C++
helpviewer_keywords:
- Picture property
- controls [MFC], OLE
- OLE controls, image
- CPictureHolder class
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14a774e3edc8b5e160b287612d3709c3424503be
ms.lasthandoff: 02/24/2017

---
# <a name="cpictureholder-class"></a>Класс CPictureHolder
Реализует свойство рисунок, который дает пользователю возможность отображать изображение в элементе управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](#cpictureholder)|Создает объект `CPictureHolder`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](#createempty)|Создает пустой объект `CPictureHolder`.|  
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Создает `CPictureHolder` объекта из растрового изображения.|  
|[CPictureHolder::CreateFromIcon](#createfromicon)|Создает `CPictureHolder` объекта из значка.|  
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Создает `CPictureHolder` объекта из метафайл.|  
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Возвращает строку, отображаемую в браузере свойств контейнер элемента управления.|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Возвращает `CPictureHolder` объекта `IDispatch` интерфейса.|  
|[CPictureHolder::GetType](#gettype)|Сообщает ли `CPictureHolder` объект является точечного рисунка, метафайла или значка.|  
|[CPictureHolder::Render](#render)|Отображает изображение.|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Наборы `CPictureHolder` объекта `IDispatch` интерфейса.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|Указатель на объект рисунка.|  
  
## <a name="remarks"></a>Примечания  
 `CPictureHolder`не имеет базового класса.  
  
 С помощью стандартных свойств изображения разработчик может указать точечного рисунка, значка или метафайла, предназначенную для отображения.  
  
 Дополнительные сведения о создании свойства пользовательских рисунков см. в статье [элементы управления ActiveX в MFC: использование изображений в элементе управления ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPictureHolder`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="cpictureholder"></a>CPictureHolder::CPictureHolder  
 Создает объект `CPictureHolder`.  
  
```  
CPictureHolder();
```  
  
##  <a name="createempty"></a>CPictureHolder::CreateEmpty  
 Создает пустой `CPictureHolder` объекта и подключает его к `IPicture` интерфейс.  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
##  <a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap  
 Использует растровое изображение для инициализации объекта рисунка в `CPictureHolder`.  
  
```  
BOOL CreateFromBitmap(
    UINT idResource);

 
BOOL CreateFromBitmap(
    CBitmap* pBitmap,  
    CPalette* pPal = NULL,  
    BOOL bTransferOwnership = TRUE);

 
BOOL CreateFromBitmap(
    HBITMAP hbm,  
    HPALETTE hpal = NULL,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `idResource`  
 Идентификатор ресурса для ресурса точечного рисунка.  
  
 `pBitmap`  
 Указатель на [CBitmap](../../mfc/reference/cbitmap-class.md) объекта.  
  
 *pPal*  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объекта.  
  
 `bTransferOwnership`  
 Указывает, берет ли объект изображения принадлежность этих объектов точечных рисунков и палитры.  
  
 `hbm`  
 Дескриптор точечного рисунка, из которого `CPictureHolder` создается объект.  
  
 `hpal`  
 Дескриптор палитры, используемой для визуализации точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий код не должен использовать растровое изображение или возвращает объект палитры каким-либо образом после этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение точечного рисунка и палитру объекты остаются действительными в течение времени существования объекта-рисунка.  
  
##  <a name="createfromicon"></a>CPictureHolder::CreateFromIcon  
 Используется для инициализации объекта рисунка в значок `CPictureHolder`.  
  
```  
BOOL CreateFromIcon(
    UINT idResource);

 
BOOL CreateFromIcon(
    HICON hIcon,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `idResource`  
 Идентификатор ресурса для ресурса точечного рисунка.  
  
 `hIcon`  
 Дескриптор значка, из которой `CPictureHolder` создается объект.  
  
 `bTransferOwnership`  
 Указывает, будет ли объект изображения стать владельцем объекта значок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий объект не следует использовать значок объекта каким-либо образом после возвращения этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение объекта значок остается действительным в течение времени существования объекта-рисунка.  
  
##  <a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile  
 Используется для инициализации объекта рисунка в метафайл `CPictureHolder`.  
  
```  
BOOL CreateFromMetafile(
    HMETAFILE hmf,  
    int xExt,  
    int yExt,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `hmf`  
 Дескриптор метафайла, используемый для создания `CPictureHolder` объекта.  
  
 *xExt*  
 X область рисунка.  
  
 *yExt*  
 Y область рисунка.  
  
 `bTransferOwnership`  
 Указывает, берет ли объект изображения владения объектом метафайла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий объект не следует использовать объекты metafile каким-либо образом после возвращения этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение метафайла объект остается действительным в течение времени существования объекта-рисунка.  
  
##  <a name="getdisplaystring"></a>CPictureHolder::GetDisplayString  
 Получает строку, которая отображается в обозревателе свойств контейнера.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Параметры  
 `strValue`  
 Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для отображения строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка успешно извлечено; в противном случае — 0.  
  
##  <a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch  
 Эта функция возвращает указатель на `CPictureHolder` объекта `IPictureDisp` интерфейса.  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPictureHolder` объекта `IPictureDisp` интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Вызывающий объект должен вызвать **версии** для этого указателя, после завершения работы с ним.  
  
##  <a name="gettype"></a>CPictureHolder::GetType  
 Указывает, является ли рисунок точечный рисунок, метафайла или значка.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее тип изображения. Возможные значения и их описание, как показано ниже:  
  
|Значение|Значение|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder`Объект unititialized.|  
|**PICTYPE_NONE**|`CPictureHolder`Объект пуст.|  
|**PICTYPE_BITMAP**|Рисунок является точечным рисунком.|  
|**PICTYPE_METAFILE**|Рисунок является метафайл.|  
|**PICTYPE_ICON**|Изображен значок.|  
  
##  <a name="m_ppict"></a>CPictureHolder::m_pPict  
 Указатель на `CPictureHolder` объекта `IPicture` интерфейса.  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="render"></a>CPictureHolder::Render  
 Отображает изображение в прямоугольнике, который ссылается `rcRender`.  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст отображения, в которой для отображения изображения.  
  
 `rcRender`  
 Прямоугольник, в котором изображен к просмотру.  
  
 *rcWBounds*  
 Прямоугольник, представляющий прямоугольник, ограничивающий объект визуализации изображения. Для управления этот прямоугольник определяется `rcBounds` параметр, передаваемый переопределение [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).  
  
##  <a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch  
 Подключается `CPictureHolder` объект `IPictureDisp` интерфейса.  
  
```  
void SetPictureDispatch(LPPICTUREDISP pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 Указатель на новый `IPictureDisp` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFontHolder](../../mfc/reference/cfontholder-class.md)

