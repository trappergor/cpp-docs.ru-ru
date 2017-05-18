---
title: "CBitmap-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- drawing, tools
- CBitmap class
- GDI bitmap
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ccfe592bbbae8c0eff22baa6e1baac56754ef6fc
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmap-class"></a>CBitmap-класс
Инкапсулирует растровое изображение интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим растровым изображением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Создает объект `CBitmap`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Инициализирует объект с аппаратно зависимый памяти точечный рисунок, заданную ширину, высоту и битовый шаблон.|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Инициализирует объект с точечным рисунком ширину, высоту и битовый шаблон (если оно указано), заданный в **точечный РИСУНОК** структуры.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Инициализирует объект с растровым изображением, чтобы он совместим с указанным устройством.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Инициализирует объект с удаляемое точечного рисунка, совместимый с указанным устройством.|  
|[CBitmap::FromHandle](#fromhandle)|Возвращает указатель на `CBitmap` объект для заданного дескриптора окна `HBITMAP` точечного рисунка.|  
|[CBitmap::GetBitmap](#getbitmap)|Заполняет **точечный РИСУНОК** структуры со сведениями о точечного рисунка.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Копирует биты растрового изображения, указанного в указанный буфер.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Возвращает ширину и высоту изображения. Высота и ширина предполагается, что заданные ранее [SetBitmapDimension](#setbitmapdimension) функции-члена.|  
|[CBitmap::LoadBitmap](#loadbitmap)|Инициализирует объект, загрузка ресурса именованного точечного рисунка из исполняемого файла приложения, подключив точечного рисунка на объект.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Загружает растровый рисунок и сопоставляет текущей цветовой палитры цветов.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Инициализирует объект, загружая предопределенные точечного рисунка Windows и присоединение точечного рисунка на объект.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Задает значение указанного бита биты растрового изображения.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Присваивает значения ширины и высоты в растровое изображение в единицах 0,1 мм.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Возвращает дескриптор Windows, присоединенные к `CBitmap` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CBitmap` объекта, создать объект, назначить ей можно с помощью функций-членов инициализации дескриптора точечного рисунка и затем вызов функций-членов объекта.  
  
 Дополнительные сведения об использовании графических объектов как `CBitmap`, в разделе [график объектов](../../mfc/graphic-objects.md).  
  
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
 Полученный объект необходимо инициализировать с помощью одного из функции-члены инициализации.  
  
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
  
 Несмотря на то, что точечный рисунок не выбираются непосредственно для устройства отображения, ее можно будет выбрать как текущий растровое изображение для «контекст памяти устройства» с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и копируются в любом контексте совместимое устройство с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) функции.  
  
 После завершения работы с объектом `CBitmap` , созданным функцией `CreateBitmap` , сначала выберите битовую карту из контекста устройства, а затем удалите объект `CBitmap` .  
  
 Дополнительные сведения см. в описании поля **bmBits** в структуре **BITMAP** . [Точечный РИСУНОК](../../mfc/reference/bitmap-structure.md) структура представлена в разделе [CBitmap::CreateBitmapIndirect](#createbitmapindirect) функции-члена.  
  
##  <a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect  
 Инициализирует точечный рисунок, ширину, высоту и битовый шаблон (если оно указано) в структуре, на который указывает `lpBitmap`.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBitmap`  
 Указывает [точечный РИСУНОК](../../mfc/reference/bitmap-structure.md) структуру, содержащую сведения о точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Несмотря на то, что точечный рисунок не выбираются непосредственно для устройства отображения, ее можно будет выбрать как текущий растровое изображение для контекста устройства памяти с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и копируются в любом контексте совместимое устройство с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) функции. ( [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) функции можно скопировать растровое изображение для текущей кисти непосредственно на контекст устройства отображения.)  
  
 Если **точечный РИСУНОК** структуры, на который указывает `lpBitmap` заполнено параметра с помощью `GetObject` функции биты растрового изображения не указаны, точечный рисунок не инициализирован. Для инициализации точечного рисунка, приложение может использовать такие как функция [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) для копирования битов из точечного рисунка, идентифицируемый первый параметр `CGdiObject::GetObject` в точечный рисунок, созданный `CreateBitmapIndirect`.  
  
 После завершения работы с `CBitmap` объект, созданный с помощью `CreateBitmapIndirect` функцию, сначала выберите точечный рисунок из контекста устройства, а затем удалить `CBitmap` объекта.  
  
##  <a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap  
 Инициализирует точечный рисунок, совместимый с устройством, определяемое `pDC`.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Задает контекст устройства.  
  
 `nWidth`  
 Задается ширина (в пикселях) битовой карты.  
  
 `nHeight`  
 Задается высота (в пикселях) битовой карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Точечный рисунок имеет одинаковое число цветовых плоскостей или совпадает с форматом битов на пиксел заданного контекста устройств. Ее можно будет выбрать как текущий растровое изображение для любых устройств памяти, совместимый с, указанного параметром `pDC`.  
  
 Если `pDC` является контекст устройства в памяти, возвращается точечный рисунок имеет тот же формат, как растровое изображение текущего выбранного в данный контекст устройства. «Контекст памяти устройства» — это блок памяти, представляющий область отображения. Он может использоваться для подготовки изображения в памяти перед их копированием на поверхность фактическому отображению совместимых устройств.  
  
 При создании контекста устройства памяти GDI автоматически выбирает монохромный точечный рисунок акций для него.  
  
 Поскольку цветовой контекст устройства в памяти может иметь цвета или выбранные монохромный точечные рисунки, возвращаемый формат растрового изображения `CreateCompatibleBitmap` функции не всегда соответствует; тем не менее, формат совместимые точечных рисунков для контекста устройств nonmemory всегда в формате устройства.  
  
 После завершения работы с `CBitmap` объект, созданный с помощью `CreateCompatibleBitmap` функцию, сначала выберите точечный рисунок из контекста устройства, а затем удалить `CBitmap` объекта.  
  
##  <a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap  
 Инициализирует удаляемое точечного рисунка, совместимый с контекста устройства, идентифицируемый `pDC`.  
  
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
 Точечный рисунок имеет одинаковое число цветовых плоскостей или совпадает с форматом битов на пиксел заданного контекста устройств. Приложения можно выбрать этот рисунок в качестве текущей битовой карты памяти устройства, совместимого с, указанного параметром `pDC`.  
  
 Windows может отменить растрового изображения, созданного с помощью функции только в том случае, если приложение не выбрана его в контексте отображения. Если Windows уничтожает точечный рисунок после не установлен, и более поздней версии приложение пытается выделить ее, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) , функция возвращает **NULL**.  
  
 После завершения работы с `CBitmap` объект, созданный с помощью `CreateDiscardableBitmap` функцию, сначала выберите точечный рисунок из контекста устройства, а затем удалить `CBitmap` объекта.  
  
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
 Если `CBitmap` объект еще не присоединен к дескриптору временный `CBitmap` объект создается и прикрепляется. Этот временный `CBitmap` допустимо только до следующей приложение имеет время простоя в свой цикл событий, после чего график все временные объекты удаляются. Другими словами является что временный объект допустима только во время обработки одного окна сообщения.  
  
##  <a name="getbitmap"></a>CBitmap::GetBitmap  
 Извлекает свойства изображения для вложенного растрового изображения.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitMap`  
 Указатель на [структуру ТОЧЕЧНОГО](../../mfc/reference/bitmap-structure.md) структуры, который будет получать свойства изображения. Этот параметр не должен иметь значение `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; в противном случае — 0.  
  
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
 Указатель на буфер, который получит точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, копируются в буфер, если метод был выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CBitmap::GetBitmap](#getbitmap) определить необходимый размер буфера.  
  
##  <a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension  
 Возвращает ширину и высоту изображения.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина и Высота растрового изображения, измеряется в единицах 0,1 мм. Высота находится в **cy** членом `CSize` , а ширина — в **cx** член. Если точечный рисунок ширины и высоты не были установлены с помощью `SetBitmapDimension`, возвращаемое значение равно 0.  
  
### <a name="remarks"></a>Примечания  
 Высота и ширина предполагается, что были заданы ранее с помощью [SetBitmapDimension](#setbitmapdimension) функции-члена.  
  
##  <a name="loadbitmap"></a>CBitmap::LoadBitmap  
 Загружает ресурс точечного рисунка, названный `lpszResourceName` или номер идентификатора в `nIDResource` из исполняемого файла приложения.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Указывает нулем строка, содержащая имя ресурса растрового изображения.  
  
 `nIDResource`  
 Указывает идентификатор ресурса ресурса растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Загруженное растровое изображение присоединяется к `CBitmap` объекта.  
  
 Если точечный рисунок идентифицируются `lpszResourceName` не существует или если недостаточно памяти для загрузки точечного рисунка, функция возвращает значение 0.  
  
 Можно использовать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) загружаться функция удалить точечный рисунок `LoadBitmap` функции или `CBitmap` деструктор будет удалить объект.  
  
> [!CAUTION]
>  Прежде чем удалить объект, убедитесь, что он не установлен в контекст устройства.  
  
 В Windows версии 3.1 и более поздних версий были добавлены следующие битовые карты:  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Эти точечные рисунки не найдены в драйверов устройств для Windows версии 3.0 и более ранних версий. Полный список точечные рисунки и отображение их внешний вид, в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap  
 Вызов этой функции-члена для загрузки точечного рисунка и сопоставления для текущей цветовой палитры цветов.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDBitmap`  
 Идентификатор ресурса растрового изображения.  
  
 `nFlags`  
 Флаг для точечного рисунка. Может быть равен нулю или **CMB_MASKED**.  
  
 `lpColorMap`  
 Указатель на **COLORMAP** структуру, содержащую цвет сведения, необходимые для сопоставления точечных рисунков. Если этот параметр равен **NULL**, функция использует карта цветов по умолчанию.  
  
 *nMapSize*  
 Количество карт цвет, на который указывает `lpColorMap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `LoadMappedBitmap` сопоставит цвета, обычно используется в глифах кнопки.  
  
 Сведения о создании сопоставленных точечного рисунка в разделе функции Windows [CreateMappedBitmap](http://go.microsoft.com/fwlink/linkid=230562) и [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap  
 Загружает предварительно определенных растровое изображение, используемое операционной системой Windows.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDBitmap`  
 Идентификационный номер предопределенные растровое изображение Windows. Ниже перечислены возможные значения из WINDOWS. H:  
  
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
 Битовая карта, имена которых начинаются с **OBM_OLD** представляют рисунки, используемые версии Windows до 3.0.  
  
 Обратите внимание, что константа **OEMRESOURCE** должен быть определен перед включением WINDOWS. H, чтобы использовать любой из **OBM_** константы.  
  
##  <a name="operator_hbitmap"></a>CBitmap::operator HBITMAP  
 Этот оператор используется получить дескриптор вложенного Windows GDI `CBitmap` объекта.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI представлена `CBitmap` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает непосредственное использование `HBITMAP` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbitmapbits"></a>CBitmap::SetBitmapBits  
 Задает биты растрового изображения до-разрядных значений, предоставленных `lpBits`.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCount`  
 Указывает число байтов, на который указывает `lpBits`.  
  
 `lpBits`  
 Указывает **БАЙТОВ** массив, содержащий значения пикселов для копирования `CBitmap` объекта. Чтобы точечный рисунок, который не может правильно отобразить изображения необходимо отформатировать значения должны соответствовать значениями глубина высота, ширина и цвет, которые были заданы при создании экземпляра CBitmap. Дополнительные сведения см. в разделе [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, используемых при задании биты растрового изображения; 0, если функция завершается с ошибкой.  
  
##  <a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension  
 Присваивает значения ширины и высоты в растровое изображение в единицах 0,1 мм.  
  
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
 Предыдущие размеры точечного рисунка. Высота — в **cy** переменной-члена `CSize` , а ширина — в **cx** переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 GDI не использует эти значения, за исключением того, чтобы вернуть их, как когда приложение вызывает [GetBitmapDimension](#getbitmapdimension) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


