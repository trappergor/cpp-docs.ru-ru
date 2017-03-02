---
title: "Класс CGdiObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGdiObject
dev_langs:
- C++
helpviewer_keywords:
- brushes, base class for
- fonts, base class for
- regions, base class for
- pens, base class for
- palettes, base class for
- CGdiObject class
- GDI objects, base class for
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
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
ms.openlocfilehash: 7fb0cd49c6a20263a5cae305b7f08f2733033ff2
ms.lasthandoff: 02/24/2017

---
# <a name="cgdiobject-class"></a>Класс CGdiObject
Предоставляет базовый класс для различных типов объектов интерфейса графических устройств Windows (GDI), таких как растровые изображения, области, кисти, перья, палитры и шрифты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|Создает объект `CGdiObject`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Присоединяет объект Windows GDI для `CGdiObject` объекта.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Возвращает дескриптор Windows предопределенные акций перья, кисти или шрифты.|  
|[CGdiObject::DeleteObject](#deleteobject)|Удаляет объект Windows GDI присоединен к `CGdiObject` объект из памяти, освобождая все системы хранения, связанный с объектом.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Удаляет все временные `CGdiObject` объектов, созданных `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор объекта Windows GDI.|  
|[CGdiObject::FromHandle](#fromhandle)|Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.|  
|[CGdiObject::GetObject](#getobject)|Заполняет буфер с данными, который описывает объект Windows GDI подключенные к `CGdiObject` объекта.|  
|[CGdiObject::GetObjectType](#getobjecttype)|Возвращает тип объекта GDI.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Возвращает `m_hObject` Если `this` — `NULL`в этом случае `NULL` возвращается.|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Сбрасывает происхождение кисти или сбрасывает логической палитры.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|Определяет, если два объекта GDI логически не равны.|  
|[CGdiObject::operator ==](#operator_eq_eq)|Определяет, логически равны ли два объекта GDI.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Извлекает `HANDLE` для присоединенного объекта Windows GDI.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|Объект `HANDLE` содержащий `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, или `HFONT` присоединен к этому объекту.|  
  
## <a name="remarks"></a>Примечания  
 Никогда не создавать `CGdiObject` напрямую. Вместо создания объекта из одного из его производных классов, таких как `CPen` или `CBrush`.  
  
 Дополнительные сведения о `CGdiObject`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-nameattacha--cgdiobjectattach"></a><a name="attach"></a>CGdiObject::Attach  
 Присоединяет объект Windows GDI для `CGdiObject` объекта.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Объект `HANDLE` в объект Windows GDI (например, `HPEN` или `HBRUSH`).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вложения прошла успешно; в противном случае — 0.  
  
##  <a name="a-namecgdiobjecta--cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>CGdiObject::CGdiObject  
 Создает объект `CGdiObject`.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CGdiObject` напрямую. Вместо создания объекта из одного из его производных классов, таких как `CPen` или **Cbrush**.  
  
##  <a name="a-namecreatestockobjecta--cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>CGdiObject::CreateStockObject  
 Получает дескриптор один из предварительно определенных стандартных перьев Windows GDI, кисти или шрифты и присоединяет объект GDI для `CGdiObject` объекта.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Константа, указывающая тип требуемого объекта акций. Параметр *fnObject* для [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] описание соответствующие значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции с помощью одного из производных классов, соответствующее типу объекта Windows GDI, например `CPen` для стандартных пера.  
  
##  <a name="a-namedeleteobjecta--cgdiobjectdeleteobject"></a><a name="deleteobject"></a>CGdiObject::DeleteObject  
 Удаляет присоединенный объект Windows GDI из памяти, освобождая все системы хранения, связанный с объектом Windows GDI.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект GDI успешно удален; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Хранилище, связанное с `CGdiObject` этот вызов не влияет на объект. Приложение не должно вызывать `DeleteObject` на `CGdiObject` объект, который выбран в данный момент в контексте устройства.  
  
 При удалении шаблона кисти растровое изображение, связанное с помощью кисти не удаляется. Точечный рисунок необходимо удалять по отдельности.  
  
##  <a name="a-namedeletetempmapa--cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>CGdiObject::DeleteTempMap  
 Вызывается автоматически `CWinApp` обработчик времени простоя `DeleteTempMap` удаляет все временные `CGdiObject` объектов, созданных `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Примечания  
 `DeleteTempMap`Отсоединяет объект Windows GDI, присоединенный к временной `CGdiObject` объекта перед удалением `CGdiObject` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#175;](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="a-namedetacha--cgdiobjectdetach"></a><a name="detach"></a>CGdiObject::Detach  
 Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор объекта Windows GDI.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HANDLE` для Windows GDI объекта отсоединенных; в противном случае **NULL** Если присоединен объект GDI.  
  
##  <a name="a-namefromhandlea--cgdiobjectfromhandle"></a><a name="fromhandle"></a>CGdiObject::FromHandle  
 Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Объект `HANDLE` в объект Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CGdiObject` , может быть временным или постоянным.  
  
### <a name="remarks"></a>Примечания  
 Если `CGdiObject` объект еще не присоединен к объекту Windows GDI временный `CGdiObject` объект создается и прикрепляется.  
  
 Этот временный `CGdiObject` допустимо только до следующего приложения имеет время простоя в свой цикл событий, в какое время будут удалены все временные графические объекты. Другими словами является что временный объект допустима только во время обработки одного окна сообщения.  
  
##  <a name="a-namegetobjecta--cgdiobjectgetobject"></a><a name="getobject"></a>CGdiObject::GetObject  
 Заполняет буфер данных, который определяет указанный объект.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nCount`  
 Указывает число байтов для копирования в `lpObject` буфера.  
  
 `lpObject`  
 Указывает пользовательские буфера, который будет получать данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, полученных; в противном случае — 0, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Функция извлекает структуру данных, тип которого зависит от типа графического объекта, как показано в следующем списке:  
  
|Объект|Тип буфера|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[ТОЧЕЧНЫЙ РИСУНОК](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Не поддерживается|  
  
 Если объект является `CBitmap` объекта, `GetObject` Возвращает ширину, высоту и цвет шрифта формат точечного рисунка. Число битов могут быть получены с помощью [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Если объект является `CPalette` объекта, `GetObject` извлекает **WORD** , указывающее количество записей в палитре. Функция не извлекает [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структура, определяющая палитры. Приложение может получить сведения о записи палитр, вызвав [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="a-namegetobjecttypea--cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>CGdiObject::GetObjectType  
 Возвращает тип объекта GDI.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип объекта, если выполнено успешно; в противном случае — 0. Значение может быть одним из следующих:  
  
- **OBJ_BITMAP** точечного рисунка  
  
- **OBJ_BRUSH** кисти  
  
- **OBJ_FONT** шрифта  
  
- **OBJ_PAL** палитры  
  
- **OBJ_PEN** пера  
  
- **OBJ_EXTPEN** Extended пера  
  
- **OBJ_REGION** область  
  
- **OBJ_DC** контекст устройства  
  
- **OBJ_MEMDC** контекст устройства в памяти  
  
- **OBJ_METAFILE** метафайл  
  
- **OBJ_METADC** метафайла контекста устройства  
  
- **OBJ_ENHMETAFILE** расширенный метафайл  
  
- **OBJ_ENHMETADC** контекст устройства Enhanced metafile  
  
##  <a name="a-namegetsafehandlea--cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>CGdiObject::GetSafeHandle  
 Возвращает `m_hObject` Если **это** — **NULL**в этом случае **NULL** возвращается.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HANDLE` в присоединенном объекте Windows GDI; в противном случае **NULL** , если объект не присоединен.  
  
### <a name="remarks"></a>Примечания  
 Это является частью парадигма интерфейс общие дескриптора и полезен, когда **NULL** недопустим или специальное значение для дескриптора.  
  
### <a name="example"></a>Пример  
  В примере показано [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="a-namemhobjecta--cgdiobjectmhobject"></a><a name="m_hobject"></a>CGdiObject::m_hObject  
 Объект `HANDLE` содержащий `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, или **HFONT** присоединен к этому объекту.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="a-nameoperatorneqa--cgdiobjectoperator-"></a><a name="operator_neq"></a>CGdiObject::operator! =  
 Определяет, если два объекта GDI логически не равны.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 Указатель на существующую `CGdiObject`.  
  
### <a name="remarks"></a>Примечания  
 Определяет, если объект GDI слева не равно объект GDI с правой стороны.  
  
##  <a name="a-nameoperatoreqeqa--cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>CGdiObject::operator ==  
 Определяет, логически равны ли два объекта GDI.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 Ссылка на существующий `CGdiObject`.  
  
### <a name="remarks"></a>Примечания  
 Определяет, равен ли объект GDI в левой части объекта GDI в правой части.  
  
##  <a name="a-nameoperatorhgdiobja--cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>CGdiObject::operator HGDIOBJ  
 Извлекает `HANDLE` в присоединенном объекте Windows GDI; в противном случае **NULL** , если объект не присоединен.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="a-nameunrealizeobjecta--cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>CGdiObject::UnrealizeObject  
 Сбрасывает происхождение кисти или сбрасывает логической палитры.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Хотя `UnrealizeObject` является функция-член `CGdiObject` класса, его следует вызывать только для `CBrush` или `CPalette` объектов.  
  
 Для `CBrush` объектов, `UnrealizeObject` направлена на Сброс начала заданного кисти в следующий раз, он установлен в контекст устройства. Если объект является `CPalette` объекта, `UnrealizeObject` указывает, что система для реализации палитры, так же, как он был ранее были Нереализованная. В следующий раз, приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) функция палитре система полностью переназначает палитре логической палитры системы.  
  
 `UnrealizeObject` Функция не должна использоваться с объектами акций. `UnrealizeObject` Функция должна вызываться всякий раз, когда устанавливается новый источник кисть (с помощью параметра [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) функции). `UnrealizeObject` Функция не должна вызываться для выбранной кисти или выбранных палитры любой контекст отображения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap-класс](../../mfc/reference/cbitmap-class.md)   
 [CBrush-класс](../../mfc/reference/cbrush-class.md)   
 [CFont-класс](../../mfc/reference/cfont-class.md)   
 [CPalette-класс](../../mfc/reference/cpalette-class.md)   
 [CPen-класс](../../mfc/reference/cpen-class.md)   
 [CRgn-класс](../../mfc/reference/crgn-class.md)

