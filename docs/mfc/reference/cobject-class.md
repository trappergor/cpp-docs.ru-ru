---
title: CObject, класс
ms.date: 11/04/2016
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
ms.openlocfilehash: 515c4e90ee6ab77a6c7c1ae108393ea1aafb7c17
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424023"
---
# <a name="cobject-class"></a>CObject, класс

Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Члены

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Description|
|----------|-----------------|
|[CObject:: CObject](#cobject)|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|Проверяет целостность этого объекта.|
|[CObject::D УМП](#dump)|Создает диагностический дамп этого объекта.|
|[CObject:: Жетрунтимекласс](#getruntimeclass)|Возвращает структуру `CRuntimeClass`, соответствующую классу данного объекта.|
|[CObject:: IsKindOf](#iskindof)|Проверяет связь этого объекта с заданным классом.|
|[CObject:: Serializable](#isserializable)|Проверяет, можно ли сериализовать этот объект.|
|[CObject:: Serialize](#serialize)|Загружает или сохраняет объект из или в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Удаление CObject:: operator](#operator_delete)|Специальный оператор **Delete** .|
|[CObject:: оператор New](#operator_new)|Специальный оператор **New** .|

## <a name="remarks"></a>Remarks

Он выступает в качестве корня не только для классов библиотек, таких как `CFile` и `CObList`, но также и для классов, которые вы пишете. `CObject` предоставляет базовые службы, включая

- Поддержка сериализации

- Сведения о классе времени выполнения

- Вывод диагностики объектов

- Совместимость с классами коллекций

Обратите внимание, что `CObject` не поддерживает множественное наследование. Производные классы могут иметь только один базовый класс `CObject`, который `CObject` должен быть крайним левым в иерархии. Однако допускается наличие структур и классов, производных от `CObject`, в правой части ветвей с множественным наследованием.

При использовании некоторых необязательных макросов в реализации и объявлениях класса вы получите значительные преимущества от `CObject`ного наследования.

Макросы первого уровня, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), допускают доступ во время выполнения к имени класса и его положению в иерархии. Это, в свою очередь, допускает осмысленную диагностическую копию.

Макросы второго уровня, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), включают все функциональные возможности макросов первого уровня, и они позволяют «сериализовать» объект в «архив» и «из него».

Сведения о наследовании классов и C++ классов Microsoft Foundation в целом и использовании `CObject`см. в разделе [Использование CObject](../../mfc/using-cobject.md) и [Serialization](../../mfc/serialization-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CObject`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="assertvalid"></a>CObject:: AssertValid

Проверяет целостность этого объекта.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Remarks

`AssertValid` выполняет проверку достоверности этого объекта, проверяя его внутреннее состояние. В отладочной версии библиотеки `AssertValid` может утверждать и, таким же, завершать программу сообщением, в котором отображается номер строки и имя файла, в котором произошел сбой утверждения.

При написании собственного класса следует переопределить функцию `AssertValid`, чтобы предоставить службы диагностики для себя и других пользователей класса. Переопределенный `AssertValid` обычно вызывает функцию `AssertValid` своего базового класса перед проверкой элементов данных, уникальных для производного класса.

Поскольку `AssertValid` является функцией **const** , вы не имеете права изменять состояние объекта во время теста. Пользовательские функции `AssertValid` производного класса не должны вызывать исключения, а должны утверждать, обнаруживают ли они недопустимые данные объекта.

Определение "допустимости" зависит от класса объекта. Как правило, функция должна выполнить «полную проверку». То есть, если объект содержит указатели на другие объекты, он должен проверить, не имеет ли указатель значение null, но не должен выполнять проверку на наличие объектов, на которые ссылаются указатели.

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Другой пример см. в разделе [афксдофораллобжектс](diagnostic-services.md#afxdoforallobjects).

##  <a name="cobject"></a>CObject:: CObject

Эти функции являются стандартными `CObject` конструкторами.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Параметры

*обжектсрк*<br/>
Ссылка на другой `CObject`

### <a name="remarks"></a>Remarks

Версия по умолчанию автоматически вызывается конструктором производного класса.

Если класс является сериализуемым (он включает в себя IMPLEMENT_SERIAL макрос), то в объявлении класса должен быть конструктор по умолчанию (конструктор без аргументов). Если конструктор по умолчанию не нужен, объявите закрытый или защищенный конструктор "Empty". Дополнительные сведения см. [в разделе Использование CObject](../../mfc/using-cobject.md).

Стандартный C++ конструктор копии класса по умолчанию выполняет копирование по элементу. Наличие закрытого `CObject` конструктора копий гарантирует сообщение об ошибке компилятора, если конструктор копии класса необходим, но недоступен. Поэтому необходимо предоставить конструктор копии, если класс требует этой возможности.

### <a name="example"></a>Пример

Список `CAge` класса, используемого в примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

##  <a name="dump"></a>CObject::D УМП

Выводит содержимое объекта в объект [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Контекст диагностического дампа для дампа обычно `afxDump`.

### <a name="remarks"></a>Remarks

При написании собственного класса следует переопределить функцию `Dump`, чтобы предоставить службы диагностики для себя и других пользователей класса. Переопределенный `Dump` обычно вызывает функцию `Dump` своего базового класса перед печатью элементов данных, уникальных для производного класса. `CObject::Dump` выводит имя класса, если в классе используется макрос `IMPLEMENT_DYNAMIC` или IMPLEMENT_SERIAL.

> [!NOTE]
>  Функция `Dump` не должна печатать символ новой строки в конце выходных данных.

`Dump` вызовы имеют смысл только в отладочной версии библиотека Microsoft Foundation Class. Для условной компиляции необходимо в скобках вызывать, объявления функций и реализации функций **#ifdef _DEBUG**/ `#endif`.

Поскольку `Dump` является функцией **const** , вы не имеете права изменять состояние объекта во время создания дампа.

[Оператор вставки CDumpContext (< <)](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызывает `Dump` при вставке `CObject` указателя.

`Dump` позволяет создавать дампы объектов только "ациклический". Можно создать дамп списка объектов, например, но если один из объектов является самим списком, то в конечном итоге стек будет переполнен.

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

##  <a name="getruntimeclass"></a>CObject:: Жетрунтимекласс

Возвращает структуру `CRuntimeClass`, соответствующую классу данного объекта.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , соответствующую классу данного объекта; никогда не **имеет значения NULL**.

### <a name="remarks"></a>Remarks

Для каждого класса, производного от `CObject`, существует одна `CRuntimeClass`ая структура. Члены структуры выглядят следующим образом:

- **LPCSTR m_lpszClassName** Строка, заканчивающаяся нулем и содержащая имя класса ASCII.

- **m_nObjectSize int** Размер объекта в байтах. Если объект содержит элементы данных, указывающие на выделенную память, размер этой памяти не включается.

- **M_wSchema uint** Номер схемы (-1 для несериализуемых классов). Описание номера схемы см. в макросе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

- **CObject\* (PASCAL\* m_pfnCreateObject) ()** Указатель на функцию конструктора по умолчанию, который создает объект класса (действителен, только если класс поддерживает динамическое создание; в противном случае возвращает **значение NULL**).

- **\* крунтимекласс (PASCAL\* m_pfn_GetBaseClass) ()** Если приложение динамически связано с AFXDLL версией MFC, то указатель на функцию, возвращающую структуру `CRuntimeClass` базового класса.

- **Крунтимекласс\* m_pBaseClass** Если приложение статически связано с MFC, то указатель на структуру `CRuntimeClass` базового класса.

Эта функция требует использования макроса [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) в реализации класса. В противном случае будут получены неверные результаты.

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

##  <a name="iskindof"></a>CObject:: IsKindOf

Проверяет связь этого объекта с заданным классом.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Параметры

*пкласс*<br/>
Указатель на структуру [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанную с классом, производным от `CObject`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект соответствует классу; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция проверяет *пкласс* , чтобы определить, является ли он объектом указанного класса или (2) является объектом класса, производного от указанного класса. Эта функция работает только для классов, объявленных с помощью макроса [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) .

Не используйте эту функцию широко, C++ так как она нарушает функцию полиморфизма. Вместо этого используйте виртуальные функции.

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

##  <a name="isserializable"></a>CObject:: Serializable

Проверяет, подходит ли этот объект для сериализации.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот объект можно сериализовать; в противном случае — 0.

### <a name="remarks"></a>Remarks

Чтобы класс был сериализуемым, его объявление должно содержать макрос [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) , а реализация должна содержать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

> [!NOTE]
>  Не переопределяйте эту функцию.

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

##  <a name="operator_delete"></a>Удаление CObject:: operator

Для окончательной версии библиотеки оператор **Delete** освобождает память, выделенную оператором **New**.

```
void PASCAL operator delete(void* p);

void PASCAL operator delete(
    void* p,
    void* pPlace);

void PASCAL operator delete(
    void* p,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Remarks

В отладочной версии оператор **Delete** участвует в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из реализаций в. CPP, будет использоваться третья версия **удаления** , в которой будут храниться имя файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении дополнительных параметров. за вас позаботится макрос.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете возможность обнаружения утечек, но без описанных выше отчетов с исходными файлами.

При переопределении операторов **New** и **Delete**Эта диагностическая функция теряется.

### <a name="example"></a>Пример

Список `CAge` класса, используемого в примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

##  <a name="operator_new"></a>CObject:: оператор New

Для окончательной версии библиотеки оператор **New** выполняет оптимальное выделение памяти таким же образом, как `malloc`.

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Remarks

В отладочной версии оператор **New** участвует в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из реализаций в. CPP, будет использоваться вторая версия **New** , в которой будут храниться имя файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении дополнительных параметров. за вас позаботится макрос.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете возможность обнаружения утечек, но без описанных выше отчетов с исходными файлами.

> [!NOTE]
>  При переопределении этого оператора необходимо также переопределить **Delete**. Не используйте стандартную библиотеку `_new_handler` функцию.

### <a name="example"></a>Пример

Список `CAge` класса, используемого в примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

##  <a name="serialize"></a>CObject:: Serialize

Считывает этот объект из архива или записывает в него.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
Объект `CArchive` для сериализации в или из.

### <a name="remarks"></a>Remarks

Необходимо переопределить `Serialize` для каждого класса, который предполагается сериализовать. Переопределенный `Serialize` должен сначала вызвать функцию `Serialize` своего базового класса.

Необходимо также использовать макрос [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) в объявлении класса, и в реализации необходимо использовать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

Используйте [CArchive:: Load](../../mfc/reference/carchive-class.md#isloading) или [CArchive::](../../mfc/reference/carchive-class.md#isstoring) , чтобы определить, загружается ли архив или сохраняется.

`Serialize` вызывается с помощью [CArchive:: вызове ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связаны с оператором вставки `CArchive` ( **<\<** ) и оператором извлечения ( **>>** ).

Примеры сериализации см. в статье [сериализация объекта](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах `CObject`, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
