---
title: "CBrush-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2c60be4501e14c1a3b55789905be1fb6e753731
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cbrush-class"></a>CBrush-класс
Инкапсулирует кисть интерфейса графических устройств Windows (GDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Создает объект `CBrush`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Инициализирует кисти стиль, цвет и шаблону, заданному в [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Инициализирует кисти шаблону, заданному аппаратно независимый точечный рисунок (DIB).|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Инициализирует с заданным шаблоном заштрихованного и цвет кисти.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Инициализирует кисти шаблону, заданному растрового изображения.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Инициализирует кисти указанным сплошным цветом.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Создает кисть, которая является системный цвет по умолчанию.|  
|[CBrush::FromHandle](#fromhandle)|Возвращает указатель на `CBrush` объект для заданного дескриптора окна `HBRUSH` объекта.|  
|[CBrush::GetLogBrush](#getlogbrush)|Возвращает [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[HBRUSH CBrush::operator](#operator_hbrush)|Возвращает дескриптор Windows, присоединенного к `CBrush` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CBrush` объектов, создания `CBrush` и передать его на любой `CDC` функция-член, требующий кисти.  
  
 Кисти может быть сплошная, hatched или узор.  
  
 Дополнительные сведения о `CBrush`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cbrush"></a>CBrush::CBrush  
 Создает объект `CBrush`.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `crColor`  
 Указывает цвет кисти в качестве цвета RGB. Если кисть hatched, этот параметр задает цвет штриховки.  
  
 `nIndex`  
 Задает стиль штриховки кисти. Он может быть одним из следующих значений:  
  
- `HS_BDIAGONAL`Штриховки вниз (слева направо) на 45 градусов  
  
- `HS_CROSS`Горизонтальные и вертикальные штриховки.  
  
- `HS_DIAGCROSS`Перекрестная штриховка на 45 градусов  
  
- `HS_FDIAGONAL`Диагональная штриховка (слева направо) на 45 градусов  
  
- `HS_HORIZONTAL`Горизонтальная штриховка  
  
- `HS_VERTICAL`Вертикальная штриховка  
  
 `pBitmap`  
 Указывает на `CBitmap` объект, который указывает, с которой кисть рисует растровое изображение.  
  
### <a name="remarks"></a>Примечания  
 `CBrush`имеет четыре перегруженные конструкторы. Конструктор без аргументов создает неинициализированный `CBrush` объект, который необходимо инициализировать, прежде чем можно будет использовать.  
  
 Если вы используете конструктор без аргументов, необходимо инициализировать итоговый `CBrush` объекта с [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), или [CreateDIBPatternBrush](#createdibpatternbrush). При использовании одного из конструкторов, которые принимают аргументы, то какой-либо дальнейшей инициализации не требуется. Конструкторы с аргументами может вызывать исключение, если возникли ошибки, хотя всегда будет успешной конструктор без аргументов.  
  
 Конструктор с одним [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр создает сплошной кисти указанным цветом. Указывает RGB-значение цвета и могут создаваться с использованием `RGB` макрос в WINDOWS. З.  
  
 Конструктор с двумя параметрами кисть штриховки. `nIndex` Указывает индекс заштрихованного шаблон. `crColor` Параметр определяет цвет.  
  
 Конструктор с `CBitmap` параметр узором кисть. Этот параметр идентифицирует растрового изображения. Битовая карта предполагается, что были созданы с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Растровое изображение, чтобы использоваться в узора заливки минимальный размер — 8 x 8 точек.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 Инициализирует кисти стиль, цвет и шаблону, заданному в [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *lpLogBrush*  
 Указывает на [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуру, содержащую сведения о кисти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Кисть, созданных с помощью монохромный (1 плоскости, 1 бит на пиксель) растрового изображения, рисуется с помощью текущих цветов текста и фона. Представленный бит установлен в 0 пикселей отображается цветом текста. Пикселей, представленный бит равен 1, будут отрисовываться цветом фона.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 Инициализирует кисти шаблону, заданному аппаратно независимый точечный рисунок (DIB).  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>Параметры  
 *hPackedDIB*  
 Определяет объект глобальной памяти, содержащий упакованный аппаратно независимый точечный рисунок (DIB).  
  
 *nUsage*  
 Указывает ли **[bmiColors]** поля [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) структура данных (в составе «упаковываются DIB») содержать явные значения RGB или индексов в момент реализованных логическую палитру. Параметр должен иметь одно из следующих значений:  
  
- **DIB_PAL_COLORS** цвет таблица состоит из массива 16-разрядными индексами.  
  
- **DIB_RGB_COLORS** таблица цветов содержит литеральные значения RGB.  
  
 *lpPackedDIB*  
 Указывает упакованный DIB, состоящий из `BITMAPINFO` структуры следовали массив байтов, определение пикселей растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть, которая впоследствии может быть выбран для любого контекста устройства, поддерживающей растровых операций.  
  
 Способ обработки DIB имеют две версии:  
  
-   В первой версии, чтобы получить дескриптор для файла DIB вызовите Windows **GlobalAlloc** функцию, чтобы выделить блок памяти, глобальные и затем заполнить упакованный DIB память.  
  
-   Во второй версии, нет необходимости вызывать **GlobalAlloc** выделить память для упакованный DIB.  
  
 Упакованный DIB состоит из `BITMAPINFO` структуру данных, которые следовали массив байтов, определяющий пикселей растрового изображения. Растровые изображения, используемых в качестве шаблонов для заполнения должны иметь размер 8 на 8 точек. Если размер точечного рисунка, Windows создает шаблон заполнения, с использованием только биты, соответствующие первые 8 строк и столбцов 8 пикселей в левом верхнем углу растрового изображения.  
  
 Когда приложение выбирает шаблон кисти DIB двух цветов в контексте монохромный устройства, Windows игнорирует цвета, указанные в DIB и отображает шаблон кисти с использованием текущих цветов текста и фона контекста устройства. — Первый цвету (со смещением 0 в таблице цветов DIB) DIB пикселей отображаются с использованием цвет текста. Пикселей второму цвету (со смещения 1 в таблице цветов), отображаются цветом фона.  
  
 Сведения об использовании следующих функций Windows см. в Windows SDK:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (эта функция предназначена только для совместимости с приложениями, созданными для версий Windows, предшествующих версии 3.0; используйте **CreateDIBPatternBrushPt** функции.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (эта функция должна использоваться для приложений на базе Win32.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 Инициализирует с заданным шаблоном заштрихованного и цвет кисти.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает стиль штриховки кисти. Он может быть одним из следующих значений:  
  
- `HS_BDIAGONAL`Штриховки вниз (слева направо) на 45 градусов  
  
- `HS_CROSS`Горизонтальные и вертикальные штриховки.  
  
- `HS_DIAGCROSS`Перекрестная штриховка на 45 градусов  
  
- `HS_FDIAGONAL`Диагональная штриховка (слева направо) на 45 градусов  
  
- `HS_HORIZONTAL`Горизонтальная штриховка  
  
- `HS_VERTICAL`Вертикальная штриховка  
  
 `crColor`  
 Указывает цвет кисти в качестве цвета RGB (Цвет штриховки). В разделе [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) в Windows SDK для получения дополнительной информации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 Инициализирует кисти шаблону, заданному растрового изображения.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Идентифицирует растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть, которая впоследствии может быть выбран для любого контекста устройства, поддерживающей растровых операций. Битовая карта, определяемый `pBitmap` обычно инициализируются с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) функции.  
  
 Растровые изображения, используемых в качестве шаблонов для заполнения должны иметь размер 8 на 8 точек. Если размер точечного рисунка, Windows будет использовать только биты, относящиеся к первые 8 строк и столбцов пикселей в левом верхнем углу растрового изображения.  
  
 Кисть шаблона могут быть удалены без влияния на связанные растрового изображения. Это означает, что растрового изображения, которые можно использовать для создать любое количество шаблон кисти.  
  
 Кисть, созданных с помощью монохромный точечный рисунок (плоскости 1 цвет 1 бит на пиксель), рисуется с помощью текущих цветов текста и фона. Представленный бит равен 0 пикселов цветом текста. Представленный равным 1 бит пикселов цветом фона.  
  
 Дополнительные сведения об использовании [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), Windows см. в разделе Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 Инициализирует кисти указанного сплошным цветом.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Параметры  
 `crColor`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) структура, которая задает цвет кисти. Указывает RGB-значение цвета и могут создаваться с использованием `RGB` макрос в WINDOWS. З.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Когда приложение завершило кисти, созданные с помощью `CreateSolidBrush`, его следует выбрать кисти из контекста устройства.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CBrush::CBrush](#cbrush).  
  
##  <a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 Инициализирует цвет кисти.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Определяет индекс как цвет. Это значение соответствует цвет, используемый для закрашивания один из элементов 21 окна. В разделе [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) в Windows SDK для списка значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Когда приложение завершило кисти, созданные с помощью `CreateSysColorBrush`, его следует выбрать кисти из контекста устройства.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>CBrush::FromHandle  
 Возвращает указатель на `CBrush` объект для заданного дескриптора окна [HBRUSH](#operator_hbrush) объекта.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `hBrush`  
 `HANDLE`кисти Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CBrush` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CBrush` объект уже не присоединен к дескриптору, временный `CBrush` объект создается и прикрепляется. Этот временный `CBrush` объект действителен только до следующего приложение имеет время простоя в цикле его событий. В настоящее время будут удалены все временные графические объекты. Другими словами временный объект является допустимым только во время обработки одного окна сообщения.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CBrush::CBrush](#cbrush).  
  
##  <a name="getlogbrush"></a>CBrush::GetLogBrush  
 Вызовите эту функцию-член для извлечения `LOGBRUSH` структуры.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogBrush`  
 Указывает на [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуру, содержащую сведения о кисти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, и `pLogBrush` является допустимым указателем, возвращаемое значение — количество байтов, сохраненных в буфере.  
  
 Если функция выполняется успешно, и `pLogBrush` — **NULL**, возвращаемое значение — число байтов, необходимое для хранения информации, функция будет храниться в буфер.  
  
 Если функция завершается с ошибкой, то возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 `LOGBRUSH` Структура определяет стиль, цвет и шаблон кисти.  
  
 Например, вызов `GetLogBrush` для соответствия определенным цветом или шаблон растрового изображения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>HBRUSH CBrush::operator  
 Этот оператор используется для получения вложенного дескриптор Windows GDI `CBrush` объекта.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI, представленных `CBrush` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает прямое использование `HBRUSH` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap-класс](../../mfc/reference/cbitmap-class.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)
