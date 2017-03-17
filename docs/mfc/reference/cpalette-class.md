---
title: "Класс CPalette | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CPalette class
- HPALETTE
- color palettes, MFC
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
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
ms.openlocfilehash: 6ccd389eaf765993c59311cc1041893f2cf9fbfa
ms.lasthandoff: 02/24/2017

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
|[CPalette::CPalette](#cpalette)|Создает `CPalette` объекта нет подключенных палитру Windows. Необходимо инициализировать `CPalette` объекта с одним из функции-члены инициализации, прежде чем можно будет использовать.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|Заменяет записи в логической палитре идентифицируется `CPalette` объекта. Приложение обновлять не требуется свою клиентскую область, поскольку Windows устанавливает новые записи в палитре системы немедленно.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Создает полутоновой палитры для контекста устройств и присоединяет его к `CPalette` объекта.|  
|[CPalette::CreatePalette](#createpalette)|Создает цветовую палитру Windows и присоединяет его к `CPalette` объекта.|  
|[CPalette::FromHandle](#fromhandle)|Возвращает указатель на `CPalette` объект для заданного дескриптора объекта палитры Windows.|  
|[CPalette::GetEntryCount](#getentrycount)|Получает число записей палитры в логической палитре.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Возвращает индекс записи в логической палитре, наиболее точно соответствующий значение цвета.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Извлекает диапазона записей палитры в логической палитре.|  
|[CPalette::ResizePalette](#resizepalette)|Изменяет размер логической палитры, определяемое `CPalette` объекта на заданное число позиций.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|Задает флаги и значения цвета RGB в диапазоне элементов в логической палитре.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|Возвращает `HPALETTE` подключен к `CPalette`.|  
  
## <a name="remarks"></a>Примечания  
 Палитра интерфейс между приложением и устройства вывода цвета (например, устройство отображения). Интерфейс позволяет приложению воспользоваться всеми преимуществами цветовые возможности устройства вывода без важности влияния цветов, отображаемых другими приложениями. Windows использует логические палитру приложения (список необходимых цветов) и системную палитру (который определяет доступные цвета), чтобы определить цвета, используемые.  
  
 Объект `CPalette` предоставляет функции-члены для управления палитры ссылается объект. Создать `CPalette` объекта и использовать его функции-члены для создания палитре фактический объект графического интерфейса (GDI) устройства и управлять его записи и другие свойства.  
  
 Дополнительные сведения об использовании `CPalette`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="animatepalette"></a>CPalette::AnimatePalette  
 Заменяет записи в логической палитре, присоединенные к `CPalette` объекта.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первую операцию в палитре для анимации.  
  
 `nNumEntries`  
 Указывает количество записей в палитре для анимации.  
  
 `lpPaletteColors`  
 Указывает на первый элемент массива [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структур для замены записи палитр, идентифицируемый `nStartIndex` и `nNumEntries`.  
  
### <a name="remarks"></a>Примечания  
 Когда приложение вызывает `AnimatePalette`, не имеет обновить свою клиентскую область, поскольку Windows устанавливает новые записи в палитре системы немедленно.  
  
 `AnimatePalette` Функция изменится только операции с **PC_RESERVED** флаг в соответствующем **palPaletteEntry** членом [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структуры, к которому присоединена `CPalette` объекта. В разделе **LOGPALETTE** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о структуре.  
  
##  <a name="cpalette"></a>CPalette::CPalette  
 Создает объект `CPalette`.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>Примечания  
 Объект не имеет подключенных палитры до вызова метода `CreatePalette` присоединить один.  
  
##  <a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette  
 Создает полутоновой палитры для контекста устройства.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Определяет контекст устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложения следует создавать полутоновой палитры, устанавливая режим растягивания контекста устройства **ПОЛУТОНОВОЙ**. Логический полутоновой палитры, возвращенный [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) функция-член затем должны быть выбран и реализованные в контекст устройства перед [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) или [StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) вызывается функция.  
  
 В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о `CreateHalftonePalette` и **StretchDIBits**.  
  
##  <a name="createpalette"></a>CPalette::CreatePalette  
 Инициализирует `CPalette` объектов путем создания логической цветовую палитру Windows и подключения его к `CPalette` объекта.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPalette`  
 Указывает [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) , содержащий сведения о цвета в палитре логической структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о **LOGPALETTE** структуры.  
  
##  <a name="fromhandle"></a>CPalette::FromHandle  
 Возвращает указатель на `CPalette` объект для заданного дескриптора объекта палитры Windows.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `hPalette`  
 Дескриптор палитры Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPalette` объекта в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CPalette` объект еще не присоединен к палитре Windows временный `CPalette` объект создается и прикрепляется. Этот временный `CPalette` допустимо только до следующей приложение имеет время простоя в свой цикл событий, после чего график все временные объекты удаляются. Другими словами временный объект является допустимым только во время обработки одного окна сообщения.  
  
##  <a name="getentrycount"></a>CPalette::GetEntryCount  
 Вызовите эту функцию-член для получения числа записей в данной логической палитре.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей в логической палитре.  
  
##  <a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 Возвращает индекс записи в логической палитры, который наиболее близко соответствует значению указанного цвета.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `crColor`  
 Задает цвет для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс записи в логической палитре. Запись содержит цвет, наиболее точно соответствующий указанным цветом.  
  
##  <a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 Извлекает диапазона записей палитры в логической палитре.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первую операцию в логической палитры для извлечения.  
  
 `nNumEntries`  
 Указывает количество записей в палитре логических требуется извлечь.  
  
 `lpPaletteColors`  
 Указывает массив [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структуры данных для получения записи палитр. Этот массив должен содержать по крайней мере столько структур данных в соответствии с `nNumEntries`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество записей, полученных из логической палитры; 0, если сбой функции.  
  
##  <a name="operator_hpalette"></a>CPalette::operator HPALETTE  
 Этот оператор используется получить дескриптор вложенного Windows GDI `CPalette` объекта.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI представлена `CPalette` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает непосредственное использование `HPALETTE` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в статье [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="resizepalette"></a>CPalette::ResizePalette  
 Изменяет размер логической палитры, присоединенные к `CPalette` объекта числу записей, определяемое `nNumEntries`.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumEntries`  
 Указывает количество записей в палитре после был изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если палитре успешно изменен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение вызывает `ResizePalette` для уменьшения размера палитры, остающихся в палитре размер записи не изменяются. Если приложение вызывает `ResizePalette` увеличить палитры, записи дополнительных палитре заданы черный (значений красного, зеленого и синего — все 0) и флаги все дополнительные записи устанавливается значение 0.  
  
 Дополнительные сведения об Windows API `ResizePalette`, в разделе [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 Задает флаги и значения цвета RGB в диапазоне элементов в логической палитре.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartIndex`  
 Указывает первую операцию в логической палитры, чтобы задать.  
  
 `nNumEntries`  
 Указывает количество записей в логической палитры, чтобы задать.  
  
 `lpPaletteColors`  
 Указывает массив [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) структуры данных для получения записи палитр. Этот массив должен содержать по крайней мере столько структур данных в соответствии с `nNumEntries`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей в палитре логический; 0, если сбой функции.  
  
### <a name="remarks"></a>Примечания  
 Если логической палитры выбирается в контексте устройства, когда приложение вызывает `SetPaletteEntries`, изменения не вступят в силу до приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Дополнительные сведения о структуре Windows **PALETTEENTRY**, в разделе [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)




