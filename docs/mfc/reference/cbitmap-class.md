---
title: "CBitmap-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs: C++
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22922d29c09ee97a8b2a292953b4bf903ab6649e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="cbitmap-class"></a>CBitmap-класс
Инкапсулирует растровое изображение интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим растровым изображением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Создает объект `CBitmap`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Инициализирует объект с растровым изображением зависящие от устройства памяти, который имеет заданную ширину, высоту и битовый шаблон.|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Инициализирует объект с точечным рисунком ширину, высоту и битовый шаблон (если оно указано), заданный в **растрового ИЗОБРАЖЕНИЯ** структуры.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Инициализирует объект с растровым изображением, чтобы она стала совместима с указанным устройством.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Инициализирует объект с удаляемое точечного рисунка, который совместим с указанным устройством.|  
|[CBitmap::FromHandle](#fromhandle)|Возвращает указатель на `CBitmap` объект для заданного дескриптора окна `HBITMAP` растрового изображения.|  
|[CBitmap::GetBitmap](#getbitmap)|Заполняет **растрового ИЗОБРАЖЕНИЯ** структуру сведениями о растрового изображения.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Копирует биты растрового изображения, указанного в указанный буфер.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Возвращает ширину и высоту точечного рисунка. Высота и ширина предполагается, что заданные ранее [SetBitmapDimension](#setbitmapdimension) функции-члена.|  
|[CBitmap::LoadBitmap](#loadbitmap)|Инициализирует объект, загрузка ресурса именованного точечного рисунка из исполняемого файла приложения, подключив точечного рисунка на объект.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Загружает точечный рисунок и сопоставляется текущей цветовой палитры цветов.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Инициализирует объект, загрузив предопределенных растрового изображения Windows и присоединение точечного рисунка на объект.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Устанавливает значения указанного бита биты растрового изображения.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Назначает ширина и Высота растрового изображения в единицах миллиметра 0,1.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[HBITMAP CBitmap::operator](#operator_hbitmap)|Возвращает дескриптор Windows, присоединенного к `CBitmap` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CBitmap` объекта, создания объекта, к ней с одним из функции-члены инициализации подключить дескриптора точечного рисунка и затем вызывать функции-члены объекта.  
  
 Дополнительные сведения об использовании графических объектов, таких как `CBitmap`, в разделе [график объектов](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cbitmap"></a>CBitmap::CBitmap  
 Создает объект `CBitmap`.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>Примечания  
 Полученный объект необходимо инициализировать с помощью одной из функций инициализации члена.  
  
##  <a name="createbitmap"></a>CBitmap::CreateBitmap  
 Инициализируется аппаратно зависимая битовая карта памяти, имеющая заданную ширину, высоту и битовый шаблон.  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Задается ширина (в пикселях) битовой карты.  
  
 `nHeight`  
 Задается высота (в пикселях) битовой карты.  
  
 `nPlanes`  
 Задается число цветовых плоскостей в битовой карте.  
  
 `nBitcount`  
 Задается число цветовых битов на пиксель отображения.  
  
 `lpBits`  
 Указывается массив байтов, содержащий исходные значения битов битовой карты. Если указывается значение **NULL**, новая битовая карта остается неинициализированной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Для цветовой битовой карты один из параметров ( `nPlanes` или `nBitcount` ) необходимо установить в значение 1. Если оба этих параметра имеют значение 1, `CreateBitmap` создает монохромную битовую карту.  
  
 Несмотря на то, что для устройства отображения нельзя напрямую выбрать растрового изображения, ее можно будет выбрать как текущую битовую карту для «контекста устройства памяти» с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и копируются в любой совместимый контекст устройства с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) функции.  
  
 После завершения работы с объектом `CBitmap` , созданным функцией `CreateBitmap` , сначала выберите битовую карту из контекста устройства, а затем удалите объект `CBitmap` .  
  
 Дополнительные сведения см. в описании поля **bmBits** в структуре **BITMAP** . [Растрового ИЗОБРАЖЕНИЯ](../../mfc/reference/bitmap-structure.md) структура рассматривается в разделе [CBitmap::CreateBitmapIndirect](#createbitmapindirect) функции-члена.  
  
##  <a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect  
 Инициализирует точечного рисунка, который имеет ширину, высоту и битовый шаблон (если оно указано) в структуре, на который указывает `lpBitmap`.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBitmap`  
 Указывает на [растрового ИЗОБРАЖЕНИЯ](../../mfc/reference/bitmap-structure.md) структуру, содержащую сведения о растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Несмотря на то, что для устройства отображения нельзя напрямую выбрать растрового изображения, ее можно будет выбрать как текущую битовую карту для контекста устройства памяти с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и копируются в любой совместимый контекст устройства с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) функции. ( [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) функции можно скопировать точечный рисунок для текущей кисти непосредственно на контекст устройства отображения.)  
  
 Если **растрового ИЗОБРАЖЕНИЯ** структуры, на который указывает `lpBitmap` параметра заполняется с помощью `GetObject` функция, биты растрового изображения не указаны и растровое изображение не инициализирован. Чтобы инициализировать растрового изображения, приложение может использовать функции например [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) копируемый биты растрового изображения, обозначенную первый параметр `CGdiObject::GetObject` к растровому изображению, созданные `CreateBitmapIndirect`.  
  
 После завершения работы с `CBitmap` объектом, созданным с помощью `CreateBitmapIndirect` функции, сначала выберите битовую карту из контекста устройства, а затем удалите `CBitmap` объекта.  
  
##  <a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap  
 Инициализирует точечного рисунка, который совместим с устройстве с `pDC`.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указывает контекст устройства.  
  
 `nWidth`  
 Задается ширина (в пикселях) битовой карты.  
  
 `nHeight`  
 Задается высота (в пикселях) битовой карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение имеет одинаковое число цветовых плоскостей или совпадает с форматом битов на пиксель заданного контекста устройств. Ее можно выбрать как текущую битовую карту для любого устройства памяти, совместимый с, указанного параметром `pDC`.  
  
 Если `pDC` является контекста устройства памяти, возвращаемый точечный рисунок имеет тот же формат, как текущий выбранный растровое изображение в этом контексте устройства. «Контекста устройства памяти» — это блок памяти, который представляет поверхность отображения. Он может использоваться для подготовки образов в памяти перед их копированием в область фактическое совместимых устройств.  
  
 При создании контекста устройства памяти GDI автоматически выбирает для него биржевых монохромный точечный рисунок.  
  
 Поскольку цвет контекста устройства памяти может иметь цвет или выбрать монохромный растровые изображения, формат растрового изображения, возвращенных `CreateCompatibleBitmap` функции не всегда соответствует; тем не менее, формат совместимого растрового изображения для контекста устройства nonmemory всегда открывается в Формат устройства.  
  
 После завершения работы с `CBitmap` объектом, созданным с помощью `CreateCompatibleBitmap` функции, сначала выберите битовую карту из контекста устройства, а затем удалите `CBitmap` объекта.  
  
##  <a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap  
 Инициализирует удаляемое точечного рисунка, который совместим с контекста устройства, обозначенную `pDC`.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указывает на контекст устройства.  
  
 `nWidth`  
 Ширина растрового изображения (в битах).  
  
 `nHeight`  
 Высота растрового изображения (в битах).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение имеет одинаковое число цветовых плоскостей или совпадает с форматом битов на пиксель заданного контекста устройств. Приложение может выбрать это растровое изображение как текущую битовую карту для памяти устройства, совместимого с, указанного параметром `pDC`.  
  
 Windows может отменить растрового изображения, созданного с помощью функции только в том случае, если приложение не выбрана его в контекст отображения. Если Windows отменяет растрового изображения при она не выделена и более поздней версии приложение пытается выделить ее, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функция возвратит **NULL**.  
  
 После завершения работы с `CBitmap` объектом, созданным с помощью `CreateDiscardableBitmap` функции, сначала выберите битовую карту из контекста устройства, а затем удалите `CBitmap` объекта.  
  
##  <a name="fromhandle"></a>CBitmap::FromHandle  
 Возвращает указатель на `CBitmap` объект для заданного дескриптора точечного рисунка Windows GDI.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Указывает точечного рисунка Windows GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CBitmap` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CBitmap` объект уже не присоединен к дескриптору, временный `CBitmap` объект создается и прикрепляется. Этот временный `CBitmap` , допустимо только до следующей приложение имеет время простоя в его цикл событий, после чего график все временные объекты удаляются. Другими словами является, что временный объект допустима только во время обработки одного окна сообщения.  
  
##  <a name="getbitmap"></a>CBitmap::GetBitmap  
 Извлекает свойства изображения для вложенного растрового изображения.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitMap`  
 Указатель на [структуру ТОЧЕЧНОГО](../../mfc/reference/bitmap-structure.md) структуру, которая будет получать свойства изображения. Этот параметр не должен иметь значение `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbitmapbits"></a>CBitmap::GetBitmapBits  
 Копирует битов растрового изображения, вложенные в указанный буфер.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwCount`  
 Число байтов для копирования в буфер.  
  
 `lpBits`  
 Указатель на буфер, который получит растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, скопировать в буфер, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CBitmap::GetBitmap](#getbitmap) определить необходимый размер буфера.  
  
##  <a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension  
 Возвращает ширину и высоту точечного рисунка.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина и Высота растрового изображения, измеряется в единицах 0,1 мм. Высота находится в **cy** членом `CSize` , а ширина — в **cx** член. Если высота и Ширина растрового изображения не были заданы с помощью `SetBitmapDimension`, возвращаемое значение равно 0.  
  
### <a name="remarks"></a>Примечания  
 Высота и ширина предполагается, что были заданы ранее с помощью [SetBitmapDimension](#setbitmapdimension) функции-члена.  
  
##  <a name="loadbitmap"></a>CBitmap::LoadBitmap  
 Загружает точечный рисунок ресурс с именем `lpszResourceName` или определены номер идентификатора в `nIDResource` из исполняемого файла приложения.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Указывает нулем строка, содержащая имя ресурса точечного рисунка.  
  
 `nIDResource`  
 Указывает количество ресурсов идентификатор ресурса точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Загрузить точечный рисунок, присоединенный к `CBitmap` объекта.  
  
 Если растровое изображение идентифицировано `lpszResourceName` не существует или если возникает нехватка памяти для загрузки растрового изображения, функция возвращает значение 0.  
  
 Можно использовать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) загрузить функцию для удаления точечного рисунка по `LoadBitmap` функция, или `CBitmap` деструктор будет удалить объект.  
  
> [!CAUTION]
>  Прежде чем удалить объект, убедитесь, что он не установлен в контекст устройства.  
  
 Были добавлены следующие битовые карты 3.1 и более поздних версиях Windows:  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Эти битовые карты не найдены в драйверы устройств для Windows версии 3.0 и более ранних версий. Полный список растровых изображений и отображение их внешний вид см. в Windows SDK.  
  
##  <a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap  
 Вызовите эту функцию-член для загрузки растрового изображения и сопоставления для текущей цветовой палитры цветов.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDBitmap`  
 Идентификатор ресурса точечного рисунка.  
  
 `nFlags`  
 Флаг для растрового изображения. Может быть равен нулю или **CMB_MASKED**.  
  
 `lpColorMap`  
 Указатель на **COLORMAP** структуру, содержащую цвет сведения, необходимые для сопоставления точечных рисунков. Если этот параметр имеет **NULL**, эта функция использует карта цветов по умолчанию.  
  
 *nMapSize*  
 Число сопоставлений цвет, на который указывает `lpColorMap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `LoadMappedBitmap` сопоставит цвета, обычно используется в глифах кнопки.  
  
 Сведения о создании сопоставленных растровое изображение в описании функции Windows [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) и [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) структуры в Windows SDK.  
  
##  <a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap  
 Загружает предварительно определенных растровое изображение, используемое операционной системой Windows.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDBitmap`  
 Идентификационный номер предопределенных растрового изображения Windows. Ниже перечислены возможные значения из WINDOWS. H:  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Битовая карта, имена которых начинаются с **OBM_OLD** представляют рисунки, используемые версии Windows до версии 3.0.  
  
 Обратите внимание, что константа **OEMRESOURCE** должен быть определен перед включением WINDOWS. H, чтобы использовать любой из **OBM_** константы.  
  
##  <a name="operator_hbitmap"></a>HBITMAP CBitmap::operator  
 Этот оператор используется для получения вложенного дескриптор Windows GDI `CBitmap` объекта.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI, представленных `CBitmap` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает прямое использование `HBITMAP` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
##  <a name="setbitmapbits"></a>CBitmap::SetBitmapBits  
 Задает биты растрового изображения для битовых значений, предоставленных `lpBits`.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCount`  
 Указывает число байтов, который указывает `lpBits`.  
  
 `lpBits`  
 Указывает на **БАЙТОВ** массив, содержащий значения для копирования в пикселах `CBitmap` объекта. Чтобы растровое изображение не может правильно отобразить изображения значения форматируются для обеспечения соответствия высоту, ширину и цвет глубина значения, заданные при создании экземпляра CBitmap. Дополнительные сведения см. в разделе [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, используемых при задании биты растрового изображения; 0, если функция завершается с ошибкой.  
  
##  <a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension  
 Назначает ширина и Высота растрового изображения в единицах миллиметра 0,1.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Ширина растрового изображения (в единицах 0,1 мм).  
  
 `nHeight`  
 Высота растрового изображения (в единицах 0,1 мм).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие аналитики растрового изображения. Высота — в **cy** переменной-члена `CSize` , а ширина — в **cx** переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 GDI не использует эти значения, за исключением того, чтобы вернуть их, как когда приложение вызывает [GetBitmapDimension](#getbitmapdimension) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

