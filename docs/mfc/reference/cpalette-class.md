---
title: CPalette-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36cc13fa77becf5bdeb3960f6ac9db18d5d63dbb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377280"
---
# <a name="cpalette-class"></a>CPalette-класс
Инкапсулирует цветовую палитру Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|Создает `CPalette` объект с присоединенного палитры Windows. Необходимо инициализировать `CPalette` объекта с помощью одного из функции-члены инициализации, прежде чем можно будет использовать.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|Заменяет записей в логическую палитру, обозначенную `CPalette` объекта. Приложение не нужно обновлять свою клиентскую область поскольку Windows немедленно сопоставляет новых записей в системной палитры.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Создает полутоновой палитры для контекста устройства и прикрепляет его к `CPalette` объекта.|  
|[CPalette::CreatePalette](#createpalette)|Создает цветовую палитру Windows и прикрепляет его к `CPalette` объекта.|  
|[CPalette::FromHandle](#fromhandle)|Возвращает указатель на `CPalette` объект для заданного дескриптора объекта палитру Windows.|  
|[CPalette::GetEntryCount](#getentrycount)|Возвращает число записей палитру в логическую палитру.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Возвращает индекс элемента в логическую палитру, который наиболее полно соответствует значение цвета.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Извлекает диапазон записей палитру в логическую палитру.|  
|[CPalette::ResizePalette](#resizepalette)|Изменяет размер логическую палитру, определяемое `CPalette` объект на указанное число записей.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|Задает значения цвета RGB и флаги в диапазоне элементов в логическую палитру.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[HPALETTE CPalette::operator](#operator_hpalette)|Возвращает `HPALETTE` присоединяется к `CPalette`.|  
  
## <a name="remarks"></a>Примечания  
 Палитра интерфейс между приложением и цвет устройство вывода (например, устройство отображения). Этот интерфейс позволяет приложению воспользоваться всеми преимуществами возможности цветов устройства вывода без важности влияния цветов, отображаемых другими приложениями. Windows использует логическую палитру приложения (список необходимых цветов) и системной палитры (который определяет доступные цвета) для определения цвета, используемые.  
  
 Объект `CPalette` предоставляет функции-члены для управления палитры ссылается объект. Создать `CPalette` и использовать свои функции-члены для создания фактического палитры объект графический интерфейс (GDI) устройства и управлять его записи и другие свойства.  
  
 Дополнительные сведения об использовании `CPalette`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="animatepalette"></a>  CPalette::AnimatePalette  
 Заменяет записей в логическую палитру, присоединенные к `CPalette` объекта.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первый элемент в палитру для анимации.  
  
 `nNumEntries`  
 Указывает количество записей в палитру для анимации.  
  
 `lpPaletteColors`  
 Указывает на первый элемент массива [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структур для замены записи палитр, обозначенную `nStartIndex` и `nNumEntries`.  
  
### <a name="remarks"></a>Примечания  
 Если приложение вызывает `AnimatePalette`, его не нужно обновлять свою клиентскую область, поскольку Windows немедленно сопоставляет новых записей в системной палитры.  
  
 `AnimatePalette` Функция изменяется только операции с **PC_RESERVED** значение в соответствующем флага **palPaletteEntry** членом [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структуры присоединенный к `CPalette` объекта. В разделе **LOGPALETTE** в Windows SDK, Дополнительные сведения об этой структуры.  
  
##  <a name="cpalette"></a>  CPalette::CPalette  
 Создает объект `CPalette`.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>Примечания  
 Объект не имеет подключенных палитры до вызова `CreatePalette` для присоединения один.  
  
##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette  
 Создает полутоновой палитры для контекста устройств.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Определяет контекст устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если имеет значение режим растягивания контекста устройства, приложения следует создать полутоновой палитры **ПОЛУТОНОВОЙ**. Логический полутоновой палитры, возвращенных [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) функция-член должна затем выбран и реализовать в контексте устройства перед [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) или [ StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) функция.  
  
 См. в Windows SDK, Дополнительные сведения `CreateHalftonePalette` и **StretchDIBits**.  
  
##  <a name="createpalette"></a>  CPalette::CreatePalette  
 Инициализирует `CPalette` объекта путем создания логических цветовую палитру Windows и подключения его к `CPalette` объекта.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPalette`  
 Указывает на [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структуру, содержащую сведения о логическую палитру цветов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 См. в Windows SDK, Дополнительные сведения **LOGPALETTE** структуры.  
  
##  <a name="fromhandle"></a>  CPalette::FromHandle  
 Возвращает указатель на `CPalette` объект для заданного дескриптора объекта палитру Windows.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `hPalette`  
 Дескриптор цветовую палитру Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPalette` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CPalette` объект уже присоединен палитры Windows временную `CPalette` объект создается и прикрепляется. Этот временный `CPalette` , допустимо только до следующей приложение имеет время простоя в его цикл событий, после чего график все временные объекты удаляются. Другими словами временный объект является допустимым только во время обработки одного окна сообщения.  
  
##  <a name="getentrycount"></a>  CPalette::GetEntryCount  
 Вызовите эту функцию-член для получения числа записей в данной логическую палитру.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество записей в логическую палитру.  
  
##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex  
 Возвращает индекс элемента в логическую палитру, который наиболее близко соответствует значению указанным цветом.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `crColor`  
 Задает цвет для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс записи в логическую палитру. Запись содержит цвет, наиболее точно соответствующий указанным цветом.  
  
##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries  
 Извлекает диапазон записей палитру в логическую палитру.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первый элемент в логическую палитру требуется получить.  
  
 `nNumEntries`  
 Указывает количество записей в логическую палитру требуется получить.  
  
 `lpPaletteColors`  
 Указывает массив [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структуры данных для получения записи палитр. Этот массив должен содержать по крайней мере столько структуры данных в соответствии с `nNumEntries`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей, полученных из логическую палитру; 0, если не удалось выполнить функцию.  
  
##  <a name="operator_hpalette"></a>  HPALETTE CPalette::operator  
 Этот оператор используется для получения вложенного дескриптор Windows GDI `CPalette` объекта.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI, представленных `CPalette` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает прямое использование `HPALETTE` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в статье [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
##  <a name="resizepalette"></a>  CPalette::ResizePalette  
 Изменяет размер логическую палитру, присоединенные к `CPalette` объекта в число записей, заданные `nNumEntries`.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumEntries`  
 Указывает количество записей в палитре после их изменять.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если палитры успешно изменен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение вызывает `ResizePalette` для уменьшения размера палитры, оставшийся размер палитры записи остаются без изменений. Если приложение вызывает `ResizePalette` увеличить палитру, заданы записи дополнительных палитр, черный цвет (красного, зеленого и синего значения: 0), а флаги для всех дополнительных записей устанавливаются в значение 0.  
  
 Дополнительные сведения об Windows API `ResizePalette`, в разделе [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) в Windows SDK.  
  
##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries  
 Задает значения цвета RGB и флаги в диапазоне элементов в логическую палитру.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первый элемент в логическую палитру требуется задать.  
  
 `nNumEntries`  
 Указывает количество записей в логическую палитру требуется задать.  
  
 `lpPaletteColors`  
 Указывает массив [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структуры данных для получения записи палитр. Этот массив должен содержать по крайней мере столько структуры данных в соответствии с `nNumEntries`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей в логическую палитру; 0, если не удалось выполнить функцию.  
  
### <a name="remarks"></a>Примечания  
 Если логическую палитру выбирается в контексте устройства, когда приложение вызывает `SetPaletteEntries`, изменения не вступят в силу до приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Дополнительные сведения о структуре Windows **PALETTEENTRY**, в разделе [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)



