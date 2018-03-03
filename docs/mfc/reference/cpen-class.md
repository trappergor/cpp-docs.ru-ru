---
title: "CPen-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51ea9aadc5d5ca8fb5a5a253d2ddb5972bf0dfdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cpen-class"></a>CPen-класс
Инкапсулирует перо интерфейса графических устройств Windows (GDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|Создает объект `CPen`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Создает логический финальных или геометрические перо с указанный стиль, ширину и атрибуты кисти и прикрепляет его к `CPen` объекта.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Создает перо с стиль, ширину и цвет, заданный [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) структуры и прикрепляет его к `CPen` объекта.|  
|[CPen::FromHandle](#fromhandle)|Возвращает указатель на `CPen` объект для заданного Windows `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Возвращает [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) базовой структуры.|  
|[CPen::GetLogPen](#getlogpen)|Возвращает [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) базовой структуры.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Возвращает дескриптор Windows, присоединенного к `CPen` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об использовании `CPen`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cpen"></a>CPen::CPen  
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
  
- **PS_DASH** создает пунктирного пера. Действительно только в том случае, когда толщина пера составляет 1 или менее, в устройстве единиц.  
  
- **PS_DOT** создает пунктирная перо. Действительно только в том случае, когда толщина пера составляет 1 или менее, в устройстве единиц.  
  
- **PS_DASHDOT** создает перо с чередованием, дефисы и точки. Действительно только в том случае, когда толщина пера составляет 1 или менее, в устройстве единиц.  
  
- **PS_DASHDOTDOT** создает перо с чередованием, дефисы и точки double. Действительно только в том случае, когда толщина пера составляет 1 или менее, в устройстве единиц.  
  
- **PS_NULL** создает null перо.  
  
- **PS_INSIDEFRAME** создает перо, рисуется линия внутри фрейма, созданные выходные данные функции Windows GDI, ограничивающий прямоугольник определяется замкнутых фигур (например, **эллипса**, **прямоугольник** , `RoundRect`, `Pie`, и `Chord` функций-членов). При использовании этого стиля с Windows GDI выходные данные функции, которые задают ограничивающий прямоугольник (например, `LineTo` функции-члена), область рисования пера не ограничивается кадра.  
  
 Вторая версия `CPen` конструктор задает сочетание типа, стиль, конец и атрибуты соединения. Значения из каждой категории следует использовать в сочетании с помощью оператора побитового или (&#124;). Тип пера может принимать одно из следующих значений:  
  
- **PS_GEOMETRIC** создает геометрические перо.  
  
- **PS_COSMETIC** создает финальных перо.  
  
     Вторая версия `CPen` конструктор добавляет следующие стили пера для `nPenStyle`:  
  
- **PS_ALTERNATE** создает перо, задающий каждого других пикселей. (Этот стиль применяется только к формальной перья.)  
  
- **PS_USERSTYLE** создает перо, использующий массив стилей, предоставленные пользователем.  
  
     Конечный маркер может принимать одно из следующих значений:  
  
- **PS_ENDCAP_ROUND** колпачки round.  
  
- **PS_ENDCAP_SQUARE** колпачки квадрат.  
  
- **PS_ENDCAP_FLAT** колпачки являются плоскими.  
  
     Соединение может быть одно из следующих значений:  
  
- **PS_JOIN_BEVEL** являются Конусные соединения.  
  
- **PS_JOIN_MITER** соединения являются углом, когда они находятся в текущем предельного значения, заданного [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) функции. Если соединение, превышает этот предел, Конусные его.  
  
- **PS_JOIN_ROUND** являются round соединения.  
  
 `nWidth`  
 Задает ширину пера.  
  
-   Для первой версии конструктора Если это значение равно 0, ширина в единицы устройства всегда равно 1 пиксель, независимо от режима сопоставления.  
  
-   Для второй версии конструктора Если `nPenStyle` — **PS_GEOMETRIC**, ширина предоставляется в логических единицах. Если `nPenStyle` — **PS_COSMETIC**, ширина должно быть установлено в 1.  
  
 `crColor`  
 Содержит цвета RGB для пера.  
  
 `pLogBrush`  
 Указывает `LOGBRUSH` структуры. Если `nPenStyle` — **PS_COSMETIC**, `lbColor` членом `LOGBRUSH` структура задает цвет пера и `lbStyle` членом `LOGBRUSH` структуры должно быть присвоено **BS_ СПЛОШНОЙ**. Если `nPenStyle` — **PS_GEOMETRIC**, все члены, которые необходимо использовать для указания атрибутов кисти пера.  
  
 `nStyleCount`  
 Указывает длину в единицах двойное `lpStyle` массива. Это значение должно быть равно нулю, если `nPenStyle` не **PS_USERSTYLE**.  
  
 `lpStyle`  
 Указывает массив значений двойное слово соответственно. Первое значение указывает длину штриха первой в пользовательский стиль, второе значение указывает длину первого пробела и т. д. Этот указатель должен быть **NULL** Если `nPenStyle` не **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Примечания  
 Если вы используете конструктор без аргументов, необходимо инициализировать итоговый `CPen` объекта с `CreatePen`, `CreatePenIndirect`, или `CreateStockObject` функции-члены.  
  
 Если вы используете конструктор, который принимает аргументы, то Дополнительная инициализация не не требуется. Конструктор аргументов может вызывать исключение, если возникли ошибки, хотя всегда будет успешной конструктор без аргументов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>CPen::CreatePen  
 Создает логический финальных или геометрические перо с указанный стиль, ширину и атрибуты кисти и прикрепляет его к `CPen` объекта.  
  
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
 Содержит цвета RGB для пера.  
  
 `pLogBrush`  
 Указывает на [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) структуры. Если `nPenStyle` — **PS_COSMETIC**, **lbColor** членом `LOGBRUSH` структура задает цвет пера и `lbStyle` членом `LOGBRUSH` структура должна быть значение **BS_SOLID**. Если **nPenStyle** — **PS_GEOMETRIC**, все члены, которые необходимо использовать для указания атрибутов кисти пера.  
  
 `nStyleCount`  
 Указывает длину в единицах двойное `lpStyle` массива. Это значение должно быть равно нулю, если `nPenStyle` не **PS_USERSTYLE**.  
  
 `lpStyle`  
 Указывает массив значений двойное слово соответственно. Первое значение указывает длину штриха первой в пользовательский стиль, второе значение указывает длину первого пробела и т. д. Этот указатель должен быть **NULL** Если `nPenStyle` не **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, или нуль, если происходит сбой метода.  
  
### <a name="remarks"></a>Примечания  
 Первая версия `CreatePen` инициализирует пера с указанный стиль, ширину и цвет. Перо может быть впоследствии выбран в качестве текущего пера для любого контекста устройства.  
  
 Перья, иметь ширину больше 1 пиксель всегда должен иметь либо **PS_NULL**, **PS_SOLID**, или **PS_INSIDEFRAME** стиля.  
  
 Если есть пера **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвета в таблице логических цветов нарисован с помощью сглаженный цвет пера. **PS_SOLID** стиль пера не может использоваться для создания с сглаженный цвет пера. Стиль **PS_INSIDEFRAME** идентична **PS_SOLID** Если толщина пера меньше или равно 1.  
  
 Вторая версия `CreatePen` инициализирует логический перо финальных или геометрические, имеющий указанный стиль, ширину и кисти атрибуты. Ширина финальных пера всегда равно 1; ширину пера геометрические всегда указывается в международных единицах измерения. После приложение создает логический перо, его можно выбрать этого пера в контексте устройства путем вызова [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функции. После выбора пера в контекст устройства, он может использоваться для рисования линий и кривых.  
  
-   Если `nPenStyle` — **PS_COSMETIC** и **PS_USERSTYLE**, записи в `lpStyle` массива укажите длину штрихов и пробелов в единицах стиля. Стиль определяются устройства, в котором используется перо, чтобы нарисовать линию.  
  
-   Если `nPenStyle` — **PS_GEOMETRIC** и **PS_USERSTYLE**, записи в `lpStyle` массива укажите длину штрихов и пробелов в логических единицах.  
  
-   Если `nPenStyle` — **PS_ALTERNATE**, единицы стиля учитывается и каждом пикселе других имеет значение.  
  
 Если приложению требуется больше заданного пера, он должен вызывать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) члена функции или уничтожить `CPen` объекта, поэтому ресурс больше не используется. Приложение не следует удалять пера при выборе в контексте устройства пера.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>CPen::CreatePenIndirect  
 Инициализирует перо, имеет стиль, ширину и цвет, заданный в структуре, на который указывает `lpLogPen`.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPen`  
 Указывает на Windows [LOGPEN](../../mfc/reference/logpen-structure.md) структуру, содержащую сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Перья, иметь ширину больше 1 пиксель всегда должен иметь либо **PS_NULL**, **PS_SOLID**, или **PS_INSIDEFRAME** стиля.  
  
 Если есть пера **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвета в таблице логических цветов нарисован с помощью сглаженный цвет пера. **PS_INSIDEFRAME** стиль идентична **PS_SOLID** Если толщина пера меньше или равно 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>CPen::FromHandle  
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
 Если объект `CPen` не прикреплен к дескриптору, создается и прикрепляется временный объект `CPen`. Этот временный `CPen` , допустимо только до следующей приложение имеет время простоя в его цикл событий, после чего график все временные объекты удаляются. Другими словами временный объект допустим только во время обработки одного окна сообщения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>CPen::GetExtLogPen  
 Возвращает **EXTLOGPEN** базовой структуры.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogPen`  
 Указывает на [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) структуру, содержащую сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **EXTLOGPEN** структура определяет стиль, ширину и атрибуты кисть фона для пера. Например, вызов `GetExtLogPen` к стилю определенного пера.  
  
 В следующих разделах в Windows SDK для получения сведений об атрибутах пера:  
  
- [Функция GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Пример  
 В следующем примере кода демонстрируется вызов `GetExtLogPen` для получения атрибутов пера, а затем создайте новый, финальных пера с тем же цветом.  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>CPen::GetLogPen  
 Возвращает `LOGPEN` базовой структуры.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Параметры  
 `pLogPen`  
 Указывает на [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) структура, содержащая сведения о пера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `LOGPEN` Структура определяет стиль, цвет и шаблон пера.  
  
 Например, вызов `GetLogPen` к стилю определенного пера.  
  
 В следующих разделах в Windows SDK для получения сведений об атрибутах пера:  
  
- [Функция GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Пример  
 В следующем примере кода демонстрируется вызов `GetLogPen` для получения перо символ, а затем создайте новый, сплошной пера с тем же цветом.  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>CPen::operator HPEN  
 Возвращает дескриптор Windows GDI вложенного `CPen` объекта.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор объекта Windows GDI, представленных `CPen` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает прямое использование `HPEN` объекта.  
  
 Дополнительные сведения об использовании графических объектов см. в статье [объектов график](http://msdn.microsoft.com/library/windows/desktop/dd144962) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CBrush](../../mfc/reference/cbrush-class.md)
