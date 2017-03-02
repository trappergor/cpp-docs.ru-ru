---
title: "CPen-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- HPEN
- CPen
dev_langs:
- C++
helpviewer_keywords:
- HPEN
- CPen class
- pens, MFC
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
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
ms.openlocfilehash: edea12c84a8f39161acbf367360fd86a1ff19998
ms.lasthandoff: 02/24/2017

---
# <a name="cpen-class"></a>CPen-класс
Инкапсулирует перо интерфейса графических устройств Windows (GDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|Создает объект `CPen`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Создает логические декоративным или геометрических пера с указанный стиль, ширину и атрибуты кисти и присоединяется к `CPen` объекта.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Создает перо с стиль, ширину и цвет в [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) структуры и присоединяет его к `CPen` объекта.|  
|[CPen::FromHandle](#fromhandle)|Возвращает указатель на `CPen` объект для заданного Windows `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Возвращает [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) базовой структуры.|  
|[CPen::GetLogPen](#getlogpen)|Возвращает [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) базовой структуры.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Возвращает дескриптор Windows, присоединенные к `CPen` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об использовании `CPen`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecpena--cpencpen"></a><a name="cpen"></a>CPen::CPen  
 Создает объект `CPen`.  
  
```  
CPen();

 
CPen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
CPen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nPenStyle`  
 Задает стиль пера. В первой версии конструктора, этот параметр может принимать одно из следующих значений:  
  
- **PS_SOLID** создает сплошной перо.  
  
- **PS_DASH** создает штрихового пера. Допустимо, только если ширину пера единиц 1 или менее, в устройстве.  
  
- **PS_DOT** создает точечный перо. Допустимо, только если ширину пера единиц 1 или менее, в устройстве.  
  
- **PS_DASHDOT** создает перо с чередованием, дефисы и точки. Допустимо, только если ширину пера единиц 1 или менее, в устройстве.  
  
- **PS_DASHDOTDOT** создает с сменяющих друг друга штрихов и double точек пера. Допустимо, только если ширину пера единиц 1 или менее, в устройстве.  
  
- **PS_NULL** создает null перо.  
  
- **PS_INSIDEFRAME** создает перо, рисующее строки внутри кадра замкнутые фигуры, созданные выходные данные функции Windows GDI, определяющие ограничивающий прямоугольник (например, **эллипс**, **прямоугольник**, `RoundRect`, `Pie`, и `Chord` функции-члены). При использовании этого стиля с Windows GDI выходные данные функции, которые задают ограничивающий прямоугольник (например, `LineTo` функции-члена), область рисования пера не ограничивается кадра.  
  
 Вторая версия `CPen` конструктор задает сочетание атрибутов соединения, конец, тип и стилей. Значения из каждой категории следует использовать в сочетании с помощью оператора побитового или (|). Тип пера может принимать одно из следующих значений:  
  
- **PS_GEOMETRIC** создает геометрические перо.  
  
- **PS_COSMETIC** создает декоративным перо.  
  
     Вторая версия `CPen` конструктор добавляет следующие стили пера для `nPenStyle`:  
  
- **PS_ALTERNATE** создает перо, которая устанавливает все пикселы. (Этот стиль применяется только для перьев, декоративным.)  
  
- **PS_USERSTYLE** создает перо, использующий массив стилей, предоставленные пользователем.  
  
     Конец может принимать одно из следующих значений:  
  
- **PS_ENDCAP_ROUND** оконечных округления.  
  
- **PS_ENDCAP_SQUARE** оконечных квадрата.  
  
- **PS_ENDCAP_FLAT** оконечных являются плоскими.  
  
     Соединение может принимать одно из следующих значений:  
  
- **PS_JOIN_BEVEL** со скошенными соединения.  
  
- **PS_JOIN_MITER** соединения являются углом, когда они находятся в текущей предельного значения, заданного [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) функции. Если соединения превышает этот предел, он является со скошенными.  
  
- **PS_JOIN_ROUND** round соединения.  
  
 `nWidth`  
 Задает ширину пера.  
  
-   Для первой версии конструктора Если это значение равно 0, ширина в единицы устройства всегда равно 1 пиксель, независимо от режима сопоставления.  
  
-   Для второй версии конструктора Если `nPenStyle` — **PS_GEOMETRIC**, ширина предоставляется в логических единицах. Если `nPenStyle` — **PS_COSMETIC**, ширина должно быть установлено в 1.  
  
 `crColor`  
 Содержит цвета в формате RGB для пера.  
  
 `pLogBrush`  
 Указывает `LOGBRUSH` структуры. Если `nPenStyle` — **PS_COSMETIC**, `lbColor` членом `LOGBRUSH` структура определяет цвет пера и `lbStyle` членом `LOGBRUSH` структуры должно быть присвоено **BS_SOLID**. Если `nPenStyle` — **PS_GEOMETRIC**, все члены должен использоваться для указания атрибутов кисти пера.  
  
 `nStyleCount`  
 Указывает длину в единицах двойное `lpStyle` массива. Это значение должно быть равно нулю, если `nPenStyle` не **PS_USERSTYLE**.  
  
 `lpStyle`  
 Указывает массив значений двойное слово соответственно. Первое значение задает длину первой штриха в пользовательский стиль, второе значение указывает длину первого пробела и т. д. Этот указатель должен быть **NULL** Если `nPenStyle` не **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Примечания  
 Если вы используете конструктор без аргументов, необходимо инициализировать итоговый `CPen` объекта с `CreatePen`, `CreatePenIndirect`, или `CreateStockObject` функции-члены.  
  
 Если вы используете конструктор, который принимает аргументы, Дополнительная инициализация не не требуется. Конструктор аргументов может создавать исключения, если возникли ошибки, хотя конструктор без аргументов всегда будет успешным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#99;](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="a-namecreatepena--cpencreatepen"></a><a name="createpen"></a>CPen::CreatePen  
 Создает логические декоративным или геометрических пера с указанный стиль, ширину и атрибуты кисти и присоединяется к `CPen` объекта.  
  
```  
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nPenStyle`  
 Задает стиль для пера. Список возможных значений см. в разделе `nPenStyle` параметр в [CPen](#cpen) конструктор.  
  
 `nWidth`  
 Задает ширину пера.  
  
-   Для первой версии `CreatePen`, если это значение равно 0, ширина в единицы устройства — 1 пиксель, независимо от режима сопоставления.  
  
-   Для второй версии `CreatePen`, если `nPenStyle` — **PS_GEOMETRIC**, ширина предоставляется в логических единицах. Если `nPenStyle` — **PS_COSMETIC**, ширина должно быть установлено в 1.  
  
 `crColor`  
 Содержит цвета в формате RGB для пера.  
  
 `pLogBrush`  
 Указывает [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры. Если `nPenStyle` — **PS_COSMETIC**, **lbColor** членом `LOGBRUSH` структура определяет цвет пера и `lbStyle` членом `LOGBRUSH` структуры должно быть присвоено **BS_SOLID**. Если **nPenStyle** — **PS_GEOMETRIC**, все члены должен использоваться для указания атрибутов кисти пера.  
  
 `nStyleCount`  
 Указывает длину в единицах двойное `lpStyle` массива. Это значение должно быть равно нулю, если `nPenStyle` не **PS_USERSTYLE**.  
  
 `lpStyle`  
 Указывает массив значений двойное слово соответственно. Первое значение задает длину первой штриха в пользовательский стиль, второе значение указывает длину первого пробела и т. д. Этот указатель должен быть **NULL** Если `nPenStyle` не **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, или нуль, если происходит сбой метода.  
  
### <a name="remarks"></a>Примечания  
 Первая версия `CreatePen` инициализирует пера с указанный стиль, ширину и цвет. Перо может быть впоследствии выбран в качестве текущего пера для любого контекста устройства.  
  
 Перья, которые имеют размер больше 1 пиксель всегда должен иметь либо **PS_NULL**, **PS_SOLID**, или **PS_INSIDEFRAME** стиль.  
  
 Если перо имеет **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвет в таблице логических цветов нарисован с помощью сглаженный цвет пера. **PS_SOLID** стиль пера не может использоваться для создания с сглаженный цвет пера. Стиль **PS_INSIDEFRAME** идентичен **PS_SOLID** Если ширину пера меньше или равно 1.  
  
 Вторая версия `CreatePen` инициализирует логический декоративным или геометрические пера, имеющий указанный стиль, ширину и кисти атрибуты. Ширину пера, декоративным всегда равно 1; ширину пера геометрические всегда указывается в международных единицах измерения. После приложение создает логический пера, его можно выбрать этого пера в контекст устройства, вызвав [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функции. После выбора пера в контекст устройства, он может использоваться для рисования линий и кривых.  
  
-   Если `nPenStyle` — **PS_COSMETIC** и **PS_USERSTYLE**, записи в `lpStyle` массива укажите длину штрихов и пробелов в единицах стиля. Единое стиля определяется устройства, в котором используется перо для рисования линии.  
  
-   Если `nPenStyle` — **PS_GEOMETRIC** и **PS_USERSTYLE**, записи в `lpStyle` массива укажите длину штрихов и пробелов в логических единицах.  
  
-   Если `nPenStyle` — **PS_ALTERNATE**, единицы стиль игнорируется и задать все пикселы.  
  
 Если приложению требуется больше заданного пера, он должен вызывать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) члена функции или уничтожить `CPen` таким образом, чтобы ресурс больше не используется. Приложение не следует удалять пера, при выборе пера в контекст устройства.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#100;](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="a-namecreatepenindirecta--cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::CreatePenIndirect  
 Инициализирует перо, имеет стиль, ширину и цвет, заданного в структуре, на который указывает `lpLogPen`.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPen`  
 Указывает Windows [LOGPEN](../../mfc/reference/logpen-structure.md) структуру, содержащую сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Перья, которые имеют размер больше 1 пиксель всегда должен иметь либо **PS_NULL**, **PS_SOLID**, или **PS_INSIDEFRAME** стиль.  
  
 Если перо имеет **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвет в таблице логических цветов нарисован с помощью сглаженный цвет пера. **PS_INSIDEFRAME** стиль идентична **PS_SOLID** Если ширину пера меньше или равно 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#101;](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="a-namefromhandlea--cpenfromhandle"></a><a name="fromhandle"></a>CPen::FromHandle  
 Возвращает указатель на `CPen` объект, заданный дескриптор для объекта pen Windows GDI.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Параметры  
 *hPen*  
 `HPEN`Дескриптор Windows GDI пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPen` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если объект `CPen` не прикреплен к дескриптору, создается и прикрепляется временный объект `CPen`. Этот временный `CPen` допустимо только до следующей приложение имеет время простоя в свой цикл событий, после чего график все временные объекты удаляются. Другими словами временный объект допустим только во время обработки одного окна сообщения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#105;](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="a-namegetextlogpena--cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen  
 Возвращает **EXTLOGPEN** базовой структуры.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogPen`  
 Указывает [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) структуру, содержащую сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **EXTLOGPEN** структура определяет стиль, ширину и кисти атрибуты пера. Например, вызов `GetExtLogPen` в соответствии со стилем, определенного для пера.  
  
 В следующих разделах в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] сведения об атрибутах пера:  
  
- [Функция GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Пример  
 В следующем примере кода демонстрируется вызов `GetExtLogPen` для извлечения атрибутов с помощью пера, а затем создать новый, декоративным пера с тем же цветом.  
  
 [!code-cpp[NVC_MFCDocView&#102;](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="a-namegetlogpena--cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen  
 Возвращает `LOGPEN` базовой структуры.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogPen`  
 Указывает [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) структура, содержащая сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `LOGPEN` Структура определяет стиль, цвет и шаблон для пера.  
  
 Например, вызов `GetLogPen` в соответствии со стилем, определенного пера.  
  
 В следующих разделах в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] сведения об атрибутах пера:  
  
- [Функция GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Пример  
 В следующем примере кода демонстрируется вызов `GetLogPen` для получения символа пера, а затем создать новый, сплошной пера с тем же цветом.  
  
 [!code-cpp[NVC_MFCDocView&#103;](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="a-nameoperatorhpena--cpenoperator-hpen"></a><a name="operator_hpen"></a>CPen::operator HPEN  
 Возвращает дескриптор вложенного Windows GDI `CPen` объекта.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI представлена `CPen` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает непосредственное использование `HPEN` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в статье [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#104;](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBrush-класс](../../mfc/reference/cbrush-class.md)

