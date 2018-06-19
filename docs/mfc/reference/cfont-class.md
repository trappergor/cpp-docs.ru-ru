---
title: CFont-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c26cf70ad52037b4ebe88b983e6d9a91273897cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369672"
---
# <a name="cfont-class"></a>CFont-класс
Инкапсулирует шрифт интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим шрифтом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|Создает объект `CFont`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|Инициализирует `CFont` с заданными характеристиками.|  
|[CFont::CreateFontIndirect](#createfontindirect)|Инициализирует `CFont` объекта с параметрами, приведенными в `LOGFONT` структуры.|  
|[CFont::CreatePointFont](#createpointfont)|Инициализирует `CFont` с указанными высотой измеряется в десятых долях точки и начертание шрифта.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|То же, что `CreateFontIndirect` за исключением того, что высота шрифта измеряется в десятых долях точки, а не логические устройства.|  
|[CFont::FromHandle](#fromhandle)|Возвращает указатель на `CFont` объект для заданного Windows **HFONT**.|  
|[CFont::GetLogFont](#getlogfont)|Заполняет `LOGFONT` со сведениями о шрифте, присоединенные к `CFont` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[HFONT CFont::operator](#operator_hfont)|Возвращает дескриптор шрифта Windows GDI присоединяется к `CFont` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CFont` объектов, создания `CFont` объекта и присоединить его с шрифт Windows [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), или [CreatePointFontIndirect](#createpointfontindirect), а затем использовать функции-члены объекта для работы с шрифта.  
  
 `CreatePointFont` И `CreatePointFontIndirect` функции часто являются проще, чем `CreateFont` или `CreateFontIndirect` так, как они выполнять преобразование высота шрифта от размера точки логические устройства автоматически.  
  
 Дополнительные сведения о `CFont`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cfont"></a>  CFont::CFont  
 Создает объект `CFont`.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Примечания  
 Полученный объект должен быть инициализирован с `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, или `CreatePointFontIndirect` прежде чем можно будет использовать.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>  CFont::CreateFont  
 Инициализирует `CFont` объекта с заданными характеристиками.  
  
```  
BOOL CreateFont(
    int nHeight,  
    int nWidth,  
    int nEscapement,  
    int nOrientation,  
    int nWeight,  
    BYTE bItalic,  
    BYTE bUnderline,  
    BYTE cStrikeOut,  
    BYTE nCharSet,  
    BYTE nOutPrecision,  
    BYTE nClipPrecision,  
    BYTE nQuality,  
    BYTE nPitchAndFamily,  
    LPCTSTR lpszFacename);
```  
  
### <a name="parameters"></a>Параметры  
 `nHeight`  
 Задает требуемую высоту (в логических единицах) шрифта. В разделе `lfHeight` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)структура в Windows SDK для описания. Абсолютное значение `nHeight` не должна превышать 16 384 единицы устройства после его преобразования. Для всех сравнений высоты средство сопоставления шрифтов ищет наибольший размер шрифта, должен превышать запрошенный размер или наименьший размер шрифта, если запрошенный размер превышает все шрифты.  
  
 `nWidth`  
 Указывает среднюю ширину (в логических единицах) символов в шрифте. Если `nWidth` равно 0, то пропорции устройства будет сопоставлена с пропорциями доступных шрифтов для нахождения ближайшего соответствия, которое определяется абсолютное значение разницы.  
  
 `nEscapement`  
 Задает угол между вектором и по оси x в отображаемой области (в единицах степень 0,1). Вектором — это линия через источники первый и последний символ в строке. Угол отсчитывается против часовой стрелки от оси x. В разделе `lfEscapement` члена в `LOGFONT` структура в Windows SDK для получения дополнительной информации.  
  
 `nOrientation`  
 Задает угол между базовым символа и оси x (в единицах степень 0,1). Угол отсчитывается против часовой стрелки от оси x для системы координат, в которых оси y вниз и по часовой стрелке относительно оси x для системы координат, в которых работает по оси y.  
  
 `nWeight`  
 Задает плотность шрифта (в пикселах замыкающей на 1000). В разделе `lfWeight` члена в `LOGFONT` структура в Windows SDK для получения дополнительной информации. Описаны значения являются приблизительными; Фактический внешний вид зависит от шрифта. Для некоторых шрифтов существуют только `FW_NORMAL`, `FW_REGULAR`, и `FW_BOLD` весовые коэффициенты. Если `FW_DONTCARE` указано, используется вес по умолчанию.  
  
 `bItalic`  
 Указывает, является ли шрифт курсивом.  
  
 `bUnderline`  
 Указывает, является ли шрифт подчеркивание.  
  
 `cStrikeOut`  
 Указывает, являются ли два прохода символов шрифта. Указывает шрифт зачеркивание, если значение ненулевое значение.  
  
 `nCharSet`  
 Указывает шрифт символа setSee `lfCharSet` члена в `LOGFONT` структура в Windows SDK для списка значений.  
  
 Набор символов OEM зависит от системы.  
  
 Шрифты с помощью других наборов символов могут существовать в системе. Приложение, использующее шрифта с набором неизвестный символ не следует пытаться преобразовать или интерпретации строк, которые должны отображаться с помощью данного шрифта. Вместо этого строки должны передаваться напрямую драйвер устройства вывода.  
  
 Средство сопоставления шрифтов не использует `DEFAULT_CHARSET` значение. Приложение может использовать это значение, чтобы разрешить имя и размер шрифта для полного описания логического шрифта. Если шрифт с указанным именем не существует, может заменить шрифт из любой набор символов для выбранного шрифта. Чтобы избежать непредвиденных результатов, приложения должны использовать `DEFAULT_CHARSET` значение только в случае необходимости.  
  
 `nOutPrecision`  
 Указывает точность нужный результат. Точность определяет, насколько точно должны соответствовать выводимых высота, ширина, ориентация символов, наклон и шаг. В разделе `lfOutPrecision` члена в `LOGFONT` структуры в Windows SDK список значений и Дополнительные сведения.  
  
 `nClipPrecision`  
 Указывает точность требуемой отсечения. Этот параметр определяет как отсекать символы, которые частично вне области обрезки. В разделе `lfClipPrecision` члена в `LOGFONT` структура в Windows SDK для списка значений.  
  
 Чтобы использовать встроенный шрифт только для чтения, приложение должно указывать `CLIP_ENCAPSULATE`.  
  
 Чтобы добиться согласованного поворот устройства, TrueType и векторных шрифтов, приложение может использовать оператор OR для объединения `CLIP_LH_ANGLES` значение с любой другой `nClipPrecision` значения. Если `CLIP_LH_ANGLES` установлен бит, поворота для всех шрифтов зависит от ориентации системы координат для левши или правая. (Дополнительные сведения о ориентацию системы координат см. в описании `nOrientation` параметров.) Если `CLIP_LH_ANGLES` является не задано, шрифты устройства всегда поворот против часовой стрелки, но зависит от ориентации системы координат поворот другие шрифты.  
  
 `nQuality`  
 Указывает качество шрифта выходных данных, которое определяет, как тщательно GDI должен добиваться соответствия параметров логического шрифта параметрам используемого физического шрифта. В разделе `lfQuality` члена в `LOGFONT` структура в Windows SDK для списка значений.  
  
 `nPitchAndFamily`  
 Задает шаг и семейство шрифта. В разделе `lfPitchAndFamily` члена в `LOGFONT` структуры в Windows SDK список значений и Дополнительные сведения.  
  
 `lpszFacename`  
 Объект `CString` или указатель на строку, завершающуюся значением null, указывающее имя гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) функцию можно использовать для перечисления всех доступных шрифтов. Если `lpszFacename` — `NULL`, GDI использует аппаратно независимые шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Шрифт впоследствии может быть выбран в качестве шрифта для любого контекста устройства.  
  
 `CreateFont` Функция не приводит к созданию нового шрифта Windows GDI. Он просто выбирает ближайшее соответствие из физических шрифты, доступные в GDI.  
  
 Приложения могут использовать параметры по умолчанию для большинства параметров при создании логического шрифта. Параметры, которые необходимо обязательно указать конкретные значения, `nHeight` и `lpszFacename`. Если `nHeight` и `lpszFacename` не установлены приложением, шрифте, созданный зависящие от устройства.  
  
 После завершения работы с `CFont` объект, созданный `CreateFont` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контекст устройства, удалите `CFont` объекта, который больше не нужен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect  
 Инициализирует `CFont` объекта с параметрами, приведенными в [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)структуры.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogFont`  
 Указывает `LOGFONT` структуры, который определяет характеристики логического шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Шрифт впоследствии может быть выбран в качестве текущий шрифт для любого устройства.  
  
 Шрифт имеет характеристики, указанный в [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры. При выборе шрифта с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функция-член, средство сопоставления шрифтов GDI пытается сопоставить шрифте с существующие физического шрифта. Если средство сопоставления шрифтов не удается найти точное совпадение для логического шрифта, он предоставляет альтернативные шрифта, характеристики которых совпадают столько запрошенного характеристики максимально.  
  
 Если требуется больше не `CFont` объект, созданный `CreateFontIndirect` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контекст устройства, удалите `CFont` объекта, который больше не нужен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>  CFont::CreatePointFont  
 Эта функция предоставляет простой способ создания указанной гарнитуры шрифта и размер в пунктах.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nPointSize`  
 Требуемая высота шрифта в десятых долях точки. (Например, передайте 120, чтобы запросить шрифта 12 пунктов.)  
  
 `lpszFaceName`  
 Объект `CString` или указатель на строку, завершающуюся значением null, указывающее имя гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows **EnumFontFamilies** функцию можно использовать для перечисления всех доступных шрифтов. Если `lpszFaceName` — **NULL**, GDI использует аппаратно независимые шрифта.  
  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объект, используемый для преобразования высоту в `nPointSize` логические устройства. Если **NULL**, на экране контекст устройства используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Он автоматически преобразует высоту в `nPointSize` логические устройства с помощью `CDC` объекта, на который указывает `pDC`.  
  
 После завершения работы с `CFont` объект, созданный `CreatePointFont` функции, сначала выбрать шрифт из контекста устройства, а затем удалите `CFont` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect  
 Эта функция является таким же, как [CreateFontIndirect](#createfontindirect) за исключением того, **lfHeight** членом `LOGFONT` интерпретируется в десятых долях точки, а не устройство единицы.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogFont`  
 Указывает на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры, который определяет характеристики логического шрифта. **LfHeight** членом `LOGFONT` структуры измеряется в десятых долях точки, а не логические устройства. (Например, задать **lfHeight** до 120, чтобы запросить шрифта 12 пунктов.)  
  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объект, используемый для преобразования высоту в **lfHeight** логические устройства. Если **NULL**, на экране контекст устройства используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция автоматически преобразует высоту в **lfHeight** логические устройства с помощью `CDC` объекта, на который указывает `pDC` перед передачей `LOGFONT` структуры систему Windows.  
  
 После завершения работы с `CFont` объект, созданный `CreatePointFontIndirect` функции, сначала выбрать шрифт из контекста устройства, а затем удалите `CFont` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CFont::FromHandle  
 Возвращает указатель на `CFont` объект для заданного **HFONT** дескриптор объекта шрифта Windows GDI.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>Параметры  
 `hFont`  
 **HFONT** дескриптор шрифта Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CFont` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CFont` объект уже не присоединен к дескриптору, временный `CFont` объект создается и прикрепляется. Этот временный `CFont` , допустимо только до следующей приложение имеет время простоя в его цикл событий, после чего график все временные объекты удаляются. Другими словами имеет временный объект является допустимым только во время обработки одного окна сообщения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>  CFont::GetLogFont  
 Эта функция вызывается для получения копии `LOGFONT` структуру `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pLogFont*  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуру для получения сведения о шрифте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполняется успешно, в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>  HFONT CFont::operator  
 Этот оператор используется для получения дескриптора Windows GDI шрифта, присоединенные к `CFont` объекта.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта шрифта Windows GDI присоединяется к `CFont` Если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Поскольку данный оператор автоматически используется для преобразования из `CFont` для [шрифты и текст](http://msdn.microsoft.com/library/windows/desktop/dd144819), можно передать `CFont` объекты функций, которые ожидают **HFONT**s.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



