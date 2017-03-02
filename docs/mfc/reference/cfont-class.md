---
title: "CFont-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFont
dev_langs:
- C++
helpviewer_keywords:
- CFont class
- GDI, font classes
- fonts, MFC classes
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
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
ms.openlocfilehash: cc7ecfb850bf24013acdb55075eeb3d64d4994ee
ms.lasthandoff: 02/24/2017

---
# <a name="cfont-class"></a>CFont-класс
Инкапсулирует шрифт интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим шрифтом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|Создает объект `CFont`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|Инициализирует `CFont` с заданными характеристиками.|  
|[CFont::CreateFontIndirect](#createfontindirect)|Инициализирует `CFont` объекта с параметрами, приведенными в `LOGFONT` структуру.|  
|[CFont::CreatePointFont](#createpointfont)|Инициализирует `CFont` с указанными высотой, измеряемый в десятых долях точки и начертания шрифта.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|То же, что `CreateFontIndirect` за исключением того, что высота шрифта измеряется в десятых долях точки, а не логические устройства.|  
|[CFont::FromHandle](#fromhandle)|Возвращает указатель на `CFont` объект для заданного Windows **HFONT**.|  
|[CFont::GetLogFont](#getlogfont)|Заполняет `LOGFONT` со сведениями о шрифте, присоединенные к `CFont` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|Возвращает дескриптор шрифта Windows GDI подключенные к `CFont` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CFont` объекта, создания `CFont` объекта и подключить его с шрифт Windows [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), или [CreatePointFontIndirect](#createpointfontindirect)и затем использовать функции-члены объекта для управления шрифта.  
  
 `CreatePointFont` И `CreatePointFontIndirect` функции часто являются проще в использовании, чем `CreateFont` или `CreateFontIndirect` так, как они выполнять преобразование высоту шрифта от размера точки логических устройств автоматически.  
  
 Дополнительные сведения о `CFont`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecfonta--cfontcfont"></a><a name="cfont"></a>CFont::CFont  
 Создает объект `CFont`.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Примечания  
 Получившийся объект должен быть инициализирован `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, или `CreatePointFontIndirect` перед его использованием.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#70;](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="a-namecreatefonta--cfontcreatefont"></a><a name="createfont"></a>CFont::CreateFont  
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
 Задает необходимую высоту шрифта (в логических единицах). В разделе `lfHeight` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] описание. Абсолютное значение `nHeight` не должно превышать 16 384 единицы устройства после его преобразования. Для всех сравнений высоты, сопоставления шрифтов ищет наибольший шрифт, не превышающий заданный размер или наименьший размер шрифта, если запрошенный размер превышает все шрифты.  
  
 `nWidth`  
 Указывает среднюю ширину (в логических единицах) символов в шрифте. Если `nWidth` равно 0, пропорции устройства будет сопоставлен с пропорциями доступных шрифтов, чтобы найти наиболее подходящие, которое определяется как абсолютное значение разницы.  
  
 `nEscapement`  
 Указывает угол между вектором и по оси x в отображаемой области (в единицах степень 0,1). Вектором — линия через источники первый и последний символ в строке. Угол отсчитывается против часовой стрелки от оси x. В разделе `lfEscapement` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
 `nOrientation`  
 Указывает угол между базовой линии символа и оси x (в единицах степень 0,1). Угол отсчитывается против часовой стрелки от оси x для системы координат, в которых оси y вниз и по часовой стрелке от оси x для системы координат, в которых работает по оси y.  
  
 `nWeight`  
 Задает плотность шрифта (в пикселах замыкающей на 1000). В разделе `lfWeight` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации. Описываются значения являются приблизительными; Фактический внешний вид зависит от шрифта. Для некоторых шрифтов существуют только `FW_NORMAL`, `FW_REGULAR`, и `FW_BOLD` веса. Если `FW_DONTCARE` заданы, используется вес по умолчанию.  
  
 `bItalic`  
 Указывает, является ли шрифт курсивом.  
  
 `bUnderline`  
 Указывает, является ли шрифт подчеркнутым.  
  
 `cStrikeOut`  
 Указывает, являются ли два прохода символов шрифта. Указывает шрифт зачеркивание, если задать ненулевое значение.  
  
 `nCharSet`  
 Определяет шрифт символа setSee `lfCharSet` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
 Набор символов OEM зависит от системы.  
  
 Шрифты с помощью других наборов символов может существовать в системе. Приложение, использующее шрифт с набором неизвестный знак не следует пытаться перевести или интерпретации строк, которые должны передаваться с помощью данного шрифта. Вместо этого строки должны быть переданы непосредственно драйвер устройства вывода.  
  
 Средство сопоставления шрифтов не использует `DEFAULT_CHARSET` значение. Приложение может использовать это значение, чтобы разрешить имя и размер шрифта для полного описания логического шрифта. Если шрифт с указанным именем не существует, можно заменить шрифт из любой набор символов для выбранного шрифта. Чтобы избежать непредвиденных результатов, приложения должны использовать `DEFAULT_CHARSET` значение только в случае необходимости.  
  
 `nOutPrecision`  
 Задает точность требуемых выходных данных. Точность определяет, насколько точно должны соответствовать выводимых высота, ширина, ориентация символов, наклон и шаг. В разделе `lfOutPrecision` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений и Дополнительные сведения.  
  
 `nClipPrecision`  
 Указывает точность отсечения требуемой. Этот параметр определяет как отсекать символы, которые частично находятся за пределами области обрезки. В разделе `lfClipPrecision` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
 Чтобы использовать встроенный шрифт только для чтения, приложение должно указать `CLIP_ENCAPSULATE`.  
  
 Чтобы добиться согласованных поворота устройства, TrueType и векторные шрифты, приложение может использовать оператор OR для объединения `CLIP_LH_ANGLES` значение с любой другой `nClipPrecision` значения. Если `CLIP_LH_ANGLES` установлен бит, поворота для всех шрифтов зависит от ориентации системы координат для левши или правши. (Дополнительные сведения об ориентации систем координат см. описание `nOrientation` параметр.) Если `CLIP_LH_ANGLES` является не задано, шрифты устройства всегда Повернуть против часовой стрелки, но поворот других шрифтов зависит от ориентации системы координат.  
  
 `nQuality`  
 Указывает качество шрифта, который определяет, как тщательно GDI должен добиваться соответствия параметров логического шрифта параметрам используемого физического шрифта. В разделе `lfQuality` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
 `nPitchAndFamily`  
 Указывает шаг и семейство шрифта. В разделе `lfPitchAndFamily` члена в `LOGFONT` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений и Дополнительные сведения.  
  
 `lpszFacename`  
 Объект `CString` или указатель нулем строку, которая указывает название гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) функция может использоваться для перечисления всех доступных шрифтов. Если `lpszFacename` — `NULL`, GDI использует аппаратно независимые шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Шрифт впоследствии может быть выбран в качестве шрифта для любого контекста устройства.  
  
 `CreateFont` Функция не создает нового шрифта Windows GDI. Он просто выбирает ближайшее соответствие из физических шрифты, доступные для GDI.  
  
 Приложения могут использовать параметры по умолчанию для большинства параметров при создании логического шрифта. Параметры, которые необходимо обязательно указать конкретные значения, `nHeight` и `lpszFacename`. Если `nHeight` и `lpszFacename` не заданы приложением, шрифте, созданный является аппаратно зависимым.  
  
 После завершения работы с `CFont` объект, созданный `CreateFont` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контекст устройства, удалите `CFont` объекта, который больше не нужен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#71;](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="a-namecreatefontindirecta--cfontcreatefontindirect"></a><a name="createfontindirect"></a>CFont::CreateFontIndirect  
 Инициализирует `CFont` объекта с параметрами, приведенными в [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)структуры.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogFont`  
 Указывает `LOGFONT` структура, которая определяет характеристики логического шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Шрифт впоследствии может быть выбран в качестве текущий шрифт для любого устройства.  
  
 Он имеет характеристики, указанного в [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры. При выборе шрифта с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функции-члена сопоставления шрифта GDI пытается сопоставить логического шрифта с помощью существующих физических шрифтов. Если средство сопоставления шрифтов не удается найти точное совпадение для логического шрифта, он предоставляет альтернативный шрифта, характеристики которых совпадают столько запрошенного характеристики максимально.  
  
 Если требуется больше не `CFont` объект, созданный `CreateFontIndirect` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контекст устройства, удалите `CFont` объекта, который больше не нужен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#72;](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="a-namecreatepointfonta--cfontcreatepointfont"></a><a name="createpointfont"></a>CFont::CreatePointFont  
 Эта функция предоставляет простой способ создать шрифт указанный шрифт и размер в пунктах.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nPointSize`  
 Требуемая высота шрифта в десятых долях точки. (Для экземпляра передайте 120, чтобы запросить шрифта 12 пунктов).  
  
 `lpszFaceName`  
 Объект `CString` или указатель нулем строку, которая указывает название гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows **EnumFontFamilies** функция может использоваться для перечисления всех доступных шрифтов. Если `lpszFaceName` — **NULL**, GDI использует аппаратно независимые шрифта.  
  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) , который может использоваться для преобразования высоту в `nPointSize` логических устройств. Если **NULL**, контекст устройства экран используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Он автоматически преобразует высоту в `nPointSize` логических устройств с помощью `CDC` объекта, на который указывает `pDC`.  
  
 После завершения работы с `CFont` объект, созданный `CreatePointFont` функцию, сначала выберите шрифт из контекста устройства, а затем удалить `CFont` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#73;](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="a-namecreatepointfontindirecta--cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect  
 Эта функция является таким же, как [CreateFontIndirect](#createfontindirect) за исключением того, что **lfHeight** членом `LOGFONT` интерпретируется в десятых долях точки, а не устройство единиц.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogFont`  
 Указывает [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структура, которая определяет характеристики логического шрифта. **LfHeight** членом `LOGFONT` структуры измеряется в десятых долях точки, а не логические устройства. (Например, задать **lfHeight** до 120, чтобы запросить шрифта 12 пунктов.)  
  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) , который может использоваться для преобразования высоту в **lfHeight** логических устройств. Если **NULL**, контекст устройства экран используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция автоматически преобразует высоту в **lfHeight** логических устройств с помощью `CDC` объекта, на который указывает `pDC` перед передачей `LOGFONT` структуры систему Windows.  
  
 После завершения работы с `CFont` объект, созданный `CreatePointFontIndirect` функцию, сначала выберите шрифт из контекста устройства, а затем удалить `CFont` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#74;](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="a-namefromhandlea--cfontfromhandle"></a><a name="fromhandle"></a>CFont::FromHandle  
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
 Если `CFont` объект еще не присоединен к дескриптору временный `CFont` объект создается и прикрепляется. Этот временный `CFont` допустимо только до следующей приложение имеет время простоя в свой цикл событий, после чего график все временные объекты удаляются. Другими словами является временный объект является допустимым только во время обработки одного окна сообщения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#75;](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="a-namegetlogfonta--cfontgetlogfont"></a><a name="getlogfont"></a>CFont::GetLogFont  
 Эта функция вызывается для получения копии `LOGFONT` структура для `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pLogFont*  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуру, чтобы получать данные о шрифте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполняется успешно, в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#76;](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="a-nameoperatorhfonta--cfontoperator-hfont"></a><a name="operator_hfont"></a>CFont::operator HFONT  
 Этот оператор используется для получения дескриптора Windows GDI шрифта, присоединенные к `CFont` объекта.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта шрифта Windows GDI присоединен к `CFont` при успехе; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Так как этот оператор автоматически используется для преобразования из `CFont` для [шрифты и текст](http://msdn.microsoft.com/library/windows/desktop/dd144819), можно передать `CFont` объектов функций, которые ожидают **HFONT**s.  
  
 Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#77;](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




