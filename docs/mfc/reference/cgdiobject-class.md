---
title: "Класс CGdiObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs: C++
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ed1c892dbd7cef4cee8281f63657144dc8dae10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CGdiObject::CreateStockObject](#createstockobject)|Получает дескриптор Windows предопределенных стандартных перья, кисти или шрифты.|  
|[CGdiObject::DeleteObject](#deleteobject)|Удаляет объект Windows GDI присоединен к `CGdiObject` объекта из памяти, освобождая все системы хранения, связанный с объектом.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Удаляет все временные `CGdiObject` объектов, созданных `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор в объект Windows GDI.|  
|[CGdiObject::FromHandle](#fromhandle)|Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.|  
|[CGdiObject::GetObject](#getobject)|Заполняет буфер с данными, который описывает объект Windows GDI присоединяется к `CGdiObject` объекта.|  
|[CGdiObject::GetObjectType](#getobjecttype)|Извлекает тип объекта GDI.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Возвращает `m_hObject` Если `this` — `NULL`в этом случае `NULL` возвращается.|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Сбрасывает источника кисти или сбрасывает логическую палитру.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|Определяет, если два объекта GDI логически не равны.|  
|[CGdiObject::operator ==](#operator_eq_eq)|Определяет, логически равны ли два объекта GDI.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Извлекает `HANDLE` в присоединенном объекте Windows GDI.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|Объект `HANDLE` содержащий `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, или `HFONT` присоединен к этому объекту.|  
  
## <a name="remarks"></a>Примечания  
 Никогда не создавайте `CGdiObject` напрямую. Вместо этого объект создается из одного из его производных классов, таких как `CPen` или `CBrush`.  
  
 Дополнительные сведения о `CGdiObject`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="attach"></a>CGdiObject::Attach  
 Присоединяет объект Windows GDI для `CGdiObject` объекта.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Объект `HANDLE` в объект Windows GDI (например, `HPEN` или `HBRUSH`).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вложение прошла успешно; в противном случае — 0.  
  
##  <a name="cgdiobject"></a>CGdiObject::CGdiObject  
 Создает объект `CGdiObject`.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CGdiObject` напрямую. Вместо этого объект создается из одного из его производных классов, таких как `CPen` или **Cbrush**.  
  
##  <a name="createstockobject"></a>CGdiObject::CreateStockObject  
 Получает дескриптор к одной из предопределенных стандартных Windows GDI перья, кисти или шрифты и присоединяет объект GDI для `CGdiObject` объекта.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Константа, указывающая тип требуемого stock-объектом. Параметр *fnObject* для [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) в Windows SDK описание соответствующие значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции с помощью одного из производных классов, соответствующее типу объектов Windows GDI, например `CPen` для биржевой пера.  
  
##  <a name="deleteobject"></a>CGdiObject::DeleteObject  
 Удаляет присоединяемый объект Windows GDI из памяти, освобождая все хранилища системы, связанный с объектом Windows GDI.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект GDI успешно удален; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Хранилище, связанное с `CGdiObject` этот вызов не влияет на объект. Приложение не должно вызывать `DeleteObject` на `CGdiObject` объекта, выбранного в данный момент в контексте устройства.  
  
 При удалении шаблона кисти растровое изображение, связанное с кистью не удаляется. Битовая карта, необходимо удалить независимо друг от друга.  
  
##  <a name="deletetempmap"></a>CGdiObject::DeleteTempMap  
 Автоматически вызывается `CWinApp` обработчиком времени простоя `DeleteTempMap` удаляет все временные `CGdiObject` объектов, созданных `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Примечания  
 `DeleteTempMap`Отсоединяет объект Windows GDI, присоединенный к временным `CGdiObject` объекта перед удалением `CGdiObject` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>CGdiObject::Detach  
 Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор в объект Windows GDI.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HANDLE` для Windows GDI объекта отсоединенных; в противном случае **NULL** Если ни один из объектов GDI подключен.  
  
##  <a name="fromhandle"></a>CGdiObject::FromHandle  
 Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `hObject`  
 Объект `HANDLE` объект Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CGdiObject` , которые могут быть постоянными или временными.  
  
### <a name="remarks"></a>Примечания  
 Если `CGdiObject` объект уже не присоединен к объектов Windows GDI, временный `CGdiObject` объект создается и прикрепляется.  
  
 Этот временный `CGdiObject` объект действителен только до следующего приложение имеет время простоя в свой цикл событий во время работы которого удаляются все временные графические объекты. Другими словами является, что временный объект допустима только во время обработки одного окна сообщения.  
  
##  <a name="getobject"></a>CGdiObject::GetObject  
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
 Указывает на буфер, предоставленный пользователем, получающего данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, полученных; в противном случае значение 0, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Функция извлекает структуру данных, тип которого зависит от типа графического объекта, как показано в следующем списке:  
  
|Объект|Тип буфера|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[РАСТРОВОЕ ИЗОБРАЖЕНИЕ](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Не поддерживается|  
  
 Если объект является `CBitmap` объекта, `GetObject` возвращает только ширину, высоту и цвет шрифта формат растрового изображения. Число битов могут быть получены с помощью [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Если объект является `CPalette` объекта, `GetObject` извлекает **WORD** , указывает количество записей в палитре. Функция не извлекает [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структура, определяющая палитры. Приложение может получить сведения о записи палитр, вызвав [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="getobjecttype"></a>CGdiObject::GetObjectType  
 Извлекает тип объекта GDI.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип объекта, в случае успешного выполнения; в противном случае — 0. Значение может быть одним из следующих:  
  
- **OBJ_BITMAP** растрового изображения  
  
- **OBJ_BRUSH** кисти  
  
- **OBJ_FONT** шрифта  
  
- **OBJ_PAL** палитры  
  
- **OBJ_PEN** пера  
  
- **OBJ_EXTPEN** расширенного пера  
  
- **OBJ_REGION** области  
  
- **OBJ_DC** контекста устройства  
  
- **OBJ_MEMDC** контекста устройства памяти  
  
- **OBJ_METAFILE** метафайл  
  
- **OBJ_METADC** контексте устройства метафайла  
  
- **OBJ_ENHMETAFILE** расширенный метафайл  
  
- **OBJ_ENHMETADC** контекст устройства расширенный метафайл  
  
##  <a name="getsafehandle"></a>CGdiObject::GetSafeHandle  
 Возвращает `m_hObject` Если **это** — **NULL**в этом случае **NULL** возвращается.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HANDLE` в присоединенном объекте Windows GDI; в противном случае **NULL** Если объект не подключен.  
  
### <a name="remarks"></a>Примечания  
 Это является частью интерфейса парадигма общие дескриптор и полезен, когда **NULL** представляет собой допустимое или специальное значение для дескриптора.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="m_hobject"></a>CGdiObject::m_hObject  
 Объект `HANDLE` содержащий `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, или **HFONT** присоединен к этому объекту.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>CGdiObject::operator! =  
 Определяет, если два объекта GDI логически не равны.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 Указатель на существующий `CGdiObject`.  
  
### <a name="remarks"></a>Примечания  
 Определяет, если объект GDI слева не равно объект GDI справа от оператора.  
  
##  <a name="operator_eq_eq"></a>CGdiObject::operator ==  
 Определяет, логически равны ли два объекта GDI.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 Ссылка на существующий `CGdiObject`.  
  
### <a name="remarks"></a>Примечания  
 Определяет, является ли объект GDI с левой стороны равно объект GDI справа от оператора.  
  
##  <a name="operator_hgdiobj"></a>CGdiObject::operator HGDIOBJ  
 Извлекает `HANDLE` в присоединенном объекте Windows GDI; в противном случае **NULL** Если объект не подключен.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>CGdiObject::UnrealizeObject  
 Сбрасывает источника кисти или сбрасывает логическую палитру.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Хотя `UnrealizeObject` является функция-член `CGdiObject` класса, он должен вызываться только на `CBrush` или `CPalette` объектов.  
  
 Для `CBrush` объектов, `UnrealizeObject` направлена на Сброс начала заданного кисти в следующий раз, он установлен в контекст устройства. Если объект является `CPalette` объекта, `UnrealizeObject` указывает системе, следует реализовать палитру, как будто он был не ранее была реализована. В следующий раз, приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) функции для палитре система полностью сопоставляет логическую палитру для системной палитры.  
  
 `UnrealizeObject` Не следует использовать функцию с объектами акций. `UnrealizeObject` Функция должна вызываться всякий раз, когда новый источник кисти имеет значение (с помощью параметра [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) функции). `UnrealizeObject` Функция не должна вызываться для выбранной кисти или выбранных палитры любой контекст отображения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap-класс](../../mfc/reference/cbitmap-class.md)   
 [CBrush-класс](../../mfc/reference/cbrush-class.md)   
 [CFont-класс](../../mfc/reference/cfont-class.md)   
 [CPalette-класс](../../mfc/reference/cpalette-class.md)   
 [CPen-класс](../../mfc/reference/cpen-class.md)   
 [Класс CRgn](../../mfc/reference/crgn-class.md)
