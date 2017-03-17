---
title: "CBrush-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- brushes, CBrush class
- CBrush class
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
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
ms.openlocfilehash: efcbe2757de3a7e4621e2b20c88726ead111cf8c
ms.lasthandoff: 02/24/2017

---
# <a name="cbrush-class"></a>CBrush-класс
Инкапсулирует кисть интерфейса графических устройств Windows (GDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Создает объект `CBrush`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Инициализирует кисть с стиль, цвет и шаблону, заданному в [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Инициализирует кисти с шаблоном, определяемое аппаратно независимые точечный рисунок (DIB).|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Инициализирует кисть с заданным шаблоном заштрихованного и цвет.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Инициализирует кисти с шаблоном, определяемое точечного рисунка.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Инициализирует кисть с указанным сплошным цветом.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Создает кисть, которая является системный цвет по умолчанию.|  
|[CBrush::FromHandle](#fromhandle)|Возвращает указатель на `CBrush` объект для заданного дескриптора окна `HBRUSH` объекта.|  
|[CBrush::GetLogBrush](#getlogbrush)|Возвращает [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|Возвращает дескриптор Windows, присоединенные к `CBrush` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CBrush` объекта, создания `CBrush` и передать его на любой `CDC` функция-член, требующий кисти.  
  
 Кисти может быть сплошной, hatched или узор.  
  
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
 Указывает цвет кисти как цвета RGB. Если кисть hatched, этот параметр задает цвет штриховки.  
  
 `nIndex`  
 Задает стиль штриховки для кисти. Это может быть одно из следующих значений:  
  
- `HS_BDIAGONAL`Штриховки вниз (слева направо) на 45 градусов  
  
- `HS_CROSS`Горизонтальные и вертикальные штриховки  
  
- `HS_DIAGCROSS`Перекрестная штриховка на 45 градусов  
  
- `HS_FDIAGONAL`Диагональная штриховка (слева направо) на 45 градусов  
  
- `HS_HORIZONTAL`Горизонтальная штриховка  
  
- `HS_VERTICAL`Вертикальная штриховка  
  
 `pBitmap`  
 Указывает `CBitmap` , указывающий точечного рисунка, с которой кисть рисует.  
  
### <a name="remarks"></a>Примечания  
 `CBrush`имеет четыре перегруженные конструкторы. Конструктор без аргументов создает неинициализированный объект `CBrush` объект, который необходимо инициализировать, прежде чем можно будет использовать.  
  
 Если вы используете конструктор без аргументов, необходимо инициализировать итоговый `CBrush` объекта с [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), или [CreateDIBPatternBrush](#createdibpatternbrush). При использовании одного из конструкторов, которые принимают аргументы, затем дальнейшая инициализация необходима. Конструкторы с аргументами может создавать исключения, если возникли ошибки, хотя конструктор без аргументов всегда будет успешным.  
  
 Конструктор с одним [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр создает сплошную кисть с указанным цветом. Цвет указывает значение RGB и могут создаваться с использованием `RGB` макрос в WINDOWS. З.  
  
 Конструктор с двумя параметрами кисть штриховки. `nIndex` Параметр указывает индекс заштрихованного шаблон. `crColor` Параметр определяет цвет.  
  
 Конструктор с `CBitmap` параметр узором кисть. Этот параметр идентифицирует точечного рисунка. Точечный рисунок предполагается, что были созданы с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Минимальный размер растрового изображения для использования в узора заливки — 8 x 8 пикселей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#21;](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 Инициализирует кисть с стиль, цвет и шаблону, заданному в [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *lpLogBrush*  
 Указывает [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуру, содержащую сведения о кисти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Кисть, созданные с помощью точечного рисунка монохромный (плоскость 1, 1 бит на пиксель), рисуется с помощью текущих цветов текста и фона. Будет отображен представлены бит установлен в 0 пикселей цветом текста. Точек, представленных бит установлен в 1 будет рисоваться с текущим цветом фона.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#22;](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 Инициализирует кисти шаблону, определяемому аппаратно независимые точечный рисунок (DIB).  
  
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
 Определяет объект глобальной памяти, содержащий упакованный аппаратно независимые точечный рисунок (DIB).  
  
 *nUsage*  
 Указывает ли **[bmiColors]** поля [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) структуру данных (в составе «упакованные DIB») содержат явные значения RGB или индексов в палитре в настоящее время реализованных логических. Параметр должен иметь одно из следующих значений:  
  
- **DIB_PAL_COLORS** таблица цветов состоит из массива 16-разрядными индексами.  
  
- **DIB_RGB_COLORS** таблица цветов содержит литеральные значения RGB.  
  
 *lpPackedDIB*  
 Указывает упакованный DIB, состоящий из `BITMAPINFO` структуры немедленно следовать массив байтов, определение пикселов точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть, которая впоследствии может быть выбран для любого контекста устройства, поддерживающий растровых операций.  
  
 Двух версий отличаются образом обработать DIB.  
  
-   В первой версии, чтобы получить дескриптор для файла DIB вызове Windows **GlobalAlloc** функцию, чтобы выделить блок памяти глобальных и затем заполнить память упакованным DIB.  
  
-   Во второй версии, не нужно вызывать **GlobalAlloc** выделить память для упакованным DIB.  
  
 Упакованный DIB состоит из `BITMAPINFO` структуру данных, немедленно следовать массив байтов, определяющий пикселов точечного рисунка. Растровые изображения, используемых в качестве шаблонов для заполнения должно быть 8 пикселей на 8 пикселей. Если размер точечного рисунка Windows создает шаблон заполнения, с использованием только биты, соответствующие первые 8 строк и столбцов 8 пикселей в левом верхнем углу точечного рисунка.  
  
 Когда приложение выбирает шаблон кисти DIB двух цветов в контексте монохромный устройства, Windows игнорирует цвета, указанные в DIB, а вместо них отображается шаблон кисти с использованием текущих цветов текста и фона контекста устройства. Пикселей сопоставляется первый цвет DIB (со смещением 0 в таблице цветов DIB) отображаются с помощью цвета текста. Пикселей сопоставляется второй цвет (со смещения 1 в таблице цветов), отображаются цветом фона.  
  
 Сведения об использовании следующих функций Windows см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (эта функция предназначена только для совместимости с приложениями, разработанными для операционных систем более ранних, чем 3.0; используйте **CreateDIBPatternBrushPt** функции.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (эта функция должна использоваться для приложений на базе Win32.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#23;](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 Инициализирует кисть с заданным шаблоном заштрихованного и цвет.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает стиль штриховки для кисти. Это может быть одно из следующих значений:  
  
- `HS_BDIAGONAL`Штриховки вниз (слева направо) на 45 градусов  
  
- `HS_CROSS`Горизонтальные и вертикальные штриховки  
  
- `HS_DIAGCROSS`Перекрестная штриховка на 45 градусов  
  
- `HS_FDIAGONAL`Диагональная штриховка (слева направо) на 45 градусов  
  
- `HS_HORIZONTAL`Горизонтальная штриховка  
  
- `HS_VERTICAL`Вертикальная штриховка  
  
 `crColor`  
 Указывает цвет кисти цветом RGB (Цвет штриховки). В разделе [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#24;](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 Инициализирует кисти с шаблоном, определяемое точечного рисунка.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Идентифицирует точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть, которая впоследствии может быть выбран для любого контекста устройства, поддерживающий растровых операций. Точечный рисунок, идентифицируемый `pBitmap` обычно инициализируются с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) функции.  
  
 Растровые изображения, используемых в качестве шаблонов для заполнения должно быть 8 пикселей на 8 пикселей. Если размер точечного рисунка Windows будет использовать только биты, соответствующие первые 8 строк и столбцов точек в левом верхнем углу точечного рисунка.  
  
 Шаблон кисти могут быть удалены не влияя на связанный точечного рисунка. Это означает, что точечный рисунок можно использовать для создать любое количество шаблон кисти.  
  
 Кисть, созданные с помощью монохромный точечный рисунок (1 цвет плоскости, 1 бит на пиксель), рисуется с помощью текущих цветов текста и фона. Представленный бит 0 пикселов цветом текста. Представленный бит установлен в 1 пикселов с текущим цветом фона.  
  
 Дополнительные сведения об использовании [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), функции Windows, в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#25;](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 Инициализирует кисти указанного сплошным цветом.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Параметры  
 `crColor`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) структура, которая задает цвет кисти. Цвет указывает значение RGB и могут создаваться с использованием `RGB` макрос в WINDOWS. З.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Когда приложение завершило кисти, созданные с помощью `CreateSolidBrush`, его следует выбрать кисти из контекста устройства.  
  
### <a name="example"></a>Пример  
  В примере показано [CBrush::CBrush](#cbrush).  
  
##  <a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 Инициализирует цвет кисти.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Определяет индекс как цвет. Это значение соответствует цвет, используемый для рисования один из элементов 21 окна. В разделе [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Кисть впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.  
  
 Когда приложение завершило кисти, созданные с помощью `CreateSysColorBrush`, его следует выбрать кисти из контекста устройства.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#26;](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
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
 Если `CBrush` объект еще не присоединен к дескриптору временный `CBrush` объект создается и прикрепляется. Этот временный `CBrush` допустимо только до следующего приложения имеет время простоя в свой цикл событий. В настоящее время будут удалены все временные графические объекты. Другими словами временный объект является допустимым только во время обработки одного окна сообщения.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CBrush::CBrush](#cbrush).  
  
##  <a name="getlogbrush"></a>CBrush::GetLogBrush  
 Вызовите эту функцию-член для получения `LOGBRUSH` структуры.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogBrush`  
 Указывает [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуру, содержащую сведения о кисти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, и `pLogBrush` является допустимым указателем, возвращается число байтов, сохраненных в буфере.  
  
 Если функция выполняется успешно, и `pLogBrush` — **NULL**, возвращаемое значение — число байтов, необходимое для хранения информации о функции будет храниться в буфер.  
  
 Если функция завершается с ошибкой, то возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 `LOGBRUSH` Структура определяет стиль, цвет и шаблон кисти.  
  
 Например, вызов `GetLogBrush` для сопоставления определенного цвета или узора точечного рисунка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#27;](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>CBrush::operator HBRUSH  
 Этот оператор используется получить дескриптор вложенного Windows GDI `CBrush` объекта.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI представлена `CBrush` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает непосредственное использование `HBRUSH` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#28;](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap-класс](../../mfc/reference/cbitmap-class.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)

