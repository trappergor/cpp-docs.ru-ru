---
title: Класс CPictureHolder | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2ffbe685ac643116fa60d4f97d03781d1efc83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cpictureholder-class"></a>Класс CPictureHolder
Реализует свойство изображение, которое дает пользователю возможность отображать изображение в элементе управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>Участники  
  
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
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Возвращает строку, отображаемую в браузере свойств контейнера элемента управления.|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Возвращает `CPictureHolder` объекта `IDispatch` интерфейса.|  
|[CPictureHolder::GetType](#gettype)|Указывает, является ли `CPictureHolder` объект является растрового изображения, значка или метафайл.|  
|[CPictureHolder::Render](#render)|Отображает изображение.|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Наборы `CPictureHolder` объекта `IDispatch` интерфейса.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|Указатель на объект изображения.|  
  
## <a name="remarks"></a>Примечания  
 `CPictureHolder` не имеет базового класса.  
  
 С помощью стандартных свойств изображения разработчик может указать растрового изображения, значка или метафайла для отображения.  
  
 Дополнительные сведения о создании настраиваемых свойствах изображения см. в статье [элементы управления MFC ActiveX: использование изображений в элементе управления ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPictureHolder`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="cpictureholder"></a>  CPictureHolder::CPictureHolder  
 Создает объект `CPictureHolder`.  
  
```  
CPictureHolder();
```  
  
##  <a name="createempty"></a>  CPictureHolder::CreateEmpty  
 Создает пустой `CPictureHolder` объекта и подключает его к `IPicture` интерфейса.  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
##  <a name="createfrombitmap"></a>  CPictureHolder::CreateFromBitmap  
 Используется для инициализации объекта изображения в растровое изображение `CPictureHolder`.  
  
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
 Идентификатор ресурса точечного рисунка ресурса.  
  
 `pBitmap`  
 Указатель на [CBitmap](../../mfc/reference/cbitmap-class.md) объекта.  
  
 *pPal*  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объекта.  
  
 `bTransferOwnership`  
 Указывает ли объект изображения будет распоряжаться объектов растрового изображения и палитру.  
  
 `hbm`  
 Дескриптор к растровому изображению, из которого `CPictureHolder` создан объект.  
  
 `hpal`  
 Дескриптор палитру, используемую для отрисовки растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий объект не следует использовать растровое изображение или возвращает объект палитры каким-либо образом, после этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение растрового изображения и палитру объекты остаются действительными в течение времени существования объекта изображения.  
  
##  <a name="createfromicon"></a>  CPictureHolder::CreateFromIcon  
 Использует значок для инициализации объекта изображения в `CPictureHolder`.  
  
```  
BOOL CreateFromIcon(
    UINT idResource);

 
BOOL CreateFromIcon(
    HICON hIcon,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `idResource`  
 Идентификатор ресурса точечного рисунка ресурса.  
  
 `hIcon`  
 Дескриптор значка, из которой `CPictureHolder` создан объект.  
  
 `bTransferOwnership`  
 Указывает, будет ли объект изображения стать владельцем объект значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий объект не следует использовать объект значка каким-либо образом после возвращения этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение объекта значок остается действительным в течение времени существования объекта изображения.  
  
##  <a name="createfrommetafile"></a>  CPictureHolder::CreateFromMetafile  
 Используется для инициализации объекта изображения в метафайл `CPictureHolder`.  
  
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
 X область изображения.  
  
 *yExt*  
 Степень Y изображения.  
  
 `bTransferOwnership`  
 Указывает ли объект изображения будет распоряжаться метафайла объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bTransferOwnership` — **TRUE**, вызывающий объект не следует использовать объекты metafile каким-либо образом после возвращения этого вызова. Если `bTransferOwnership` — **FALSE**, вызывающий объект отвечает за обеспечение метафайла объект остается действительным в течение времени существования объекта изображения.  
  
##  <a name="getdisplaystring"></a>  CPictureHolder::GetDisplayString  
 Получает строку, которая отображается в обозревателе свойств контейнера.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Параметры  
 `strValue`  
 Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для хранения отображаемой строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка успешно извлечено; в противном случае — 0.  
  
##  <a name="getpicturedispatch"></a>  CPictureHolder::GetPictureDispatch  
 Эта функция возвращает указатель на `CPictureHolder` объекта `IPictureDisp` интерфейса.  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPictureHolder` объекта `IPictureDisp` интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Вызывающий объект должен вызвать **выпуска** для этого указателя, когда завершит работу с ней.  
  
##  <a name="gettype"></a>  CPictureHolder::GetType  
 Указывает, является ли изображение точечного рисунка, метафайла или значок.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее тип изображения. Возможные значения и их значение представлено следующим образом:  
  
|Значение|Значение|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder` Объект unititialized.|  
|**PICTYPE_NONE**|`CPictureHolder` Объект пуст.|  
|**PICTYPE_BITMAP**|Рисунок является точечным рисунком.|  
|**PICTYPE_METAFILE**|Рисунок является метафайл.|  
|**PICTYPE_ICON**|Изображен значок.|  
  
##  <a name="m_ppict"></a>  CPictureHolder::m_pPict  
 Указатель на `CPictureHolder` объекта `IPicture` интерфейса.  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="render"></a>  CPictureHolder::Render  
 Отображает изображение в прямоугольник, который ссылается `rcRender`.  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст отображения, в котором должен быть подготовлен к просмотру изображения.  
  
 `rcRender`  
 Прямоугольник, в котором изображен должен быть подготовлен к просмотру.  
  
 *rcWBounds*  
 Прямоугольник, представляющий ограничивающий прямоугольник объекта отрисовки рисунка. Для элемента управления этот прямоугольник определяется `rcBounds` передан параметр переопределения [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).  
  
##  <a name="setpicturedispatch"></a>  CPictureHolder::SetPictureDispatch  
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
