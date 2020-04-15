---
title: Класс CObject
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
ms.openlocfilehash: cea4d09a1c1a4680b095a40fa0619287959ff4ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360427"
---
# <a name="cobject-class"></a>Класс CObject

Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[Объект::Объект](#cobject)|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Объект::AssertValid](#assertvalid)|Проверяет целостность этого объекта.|
|[Кобъект::D](#dump)|Производит диагностическую свалку этого объекта.|
|[Объект::GetRuntimeClass](#getruntimeclass)|Возвращает `CRuntimeClass` структуру, соответствующую классу этого объекта.|
|[Объект::IsKindOf](#iskindof)|Тестирует отношение этого объекта к данному классу.|
|[CObject::IsSerializable](#isserializable)|Тесты, чтобы увидеть, можно ли сериализировать этот объект.|
|[CObject::Serialize](#serialize)|Загружает или хранит объект из/в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CObject::оператор удалить](#operator_delete)|Специальный оператор **удаления.**|
|[CObject::оператор новый](#operator_new)|Специальный **новый** оператор.|

## <a name="remarks"></a>Remarks

Он служит корнем не только для `CFile` `CObList`библиотечных классов, таких как и , но и для классов, которые вы пишете. `CObject`основные услуги, в том числе

- Поддержка сериализации

- Информация о забеге класса

- Вывод ы диагностики объектов

- Совместимость с классами коллекций

Обратите `CObject` внимание, что не поддерживает несколько наследований. Ваши классы могут иметь `CObject` только один `CObject` базовый класс, и он должен быть оставлен в иерархии. Допустимо, однако, иметь структуры и `CObject`не-полученные классы в правосторонних ветвях с несколькими наследственными.

Вы поймете основные преимущества от `CObject` производной, если вы используете некоторые из дополнительных макросов в реализации и декларациях класса.

Макросы первого уровня, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC,](run-time-object-model-services.md#implement_dynamic)позволяют получить доступ к названию класса и его положению в иерархии. Это, в свою очередь, позволяет осмысленно проводить диагностический демпинг.

Макросы второго уровня, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL,](run-time-object-model-services.md#implement_serial)включают в себя все функциональные возможности макросов первого уровня, и они позволяют объекту быть «серийным» к «архиву» и из него.

Для получения информации о произвобальных классах `CObject`Фонда Майкрософт и [Serialization](../../mfc/serialization-in-mfc.md)классах СЗ в целом и [см.](../../mfc/using-cobject.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CObject`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>Объект::AssertValid

Проверяет целостность этого объекта.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Remarks

`AssertValid`выполняет проверку достоверности этого объекта, проверяя его внутреннее состояние. В версии Debug библиотеки `AssertValid` может утверждать и, таким образом, прекращать программу с сообщением, в котором перечислены номер строки и имя файла, где утверждение не удалось.

Когда вы пишете свой собственный `AssertValid` класс, вы должны переопределить функцию для предоставления диагностических услуг для себя и других пользователей вашего класса. Перерегистрированный `AssertValid` обычно `AssertValid` вызывает функцию своего базового класса, прежде чем проверять данные, уникальные для производного класса.

Поскольку `AssertValid` функция **const** является недопустимой для изменения состояния объекта во время теста. Ваши собственные функции производных классов `AssertValid` не должны бросать исключения, а должны утверждать, обнаруживают ли они недействительные данные объектов.

Определение "действительность" зависит от класса объекта. Как правило, функция должна выполнять "неглубокую проверку". То есть, если объект содержит указатели на другие объекты, он должен проверить, не являются ли указатели недействительными, но он не должен выполнять тестирование действительности на объектах, упомянутых указатели.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Для другого [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)примера см.

## <a name="cobjectcobject"></a><a name="cobject"></a>Объект::Объект

Эти функции `CObject` являются стандартными конструкторами.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Параметры

*objectSrc*<br/>
Ссылка на другой`CObject`

### <a name="remarks"></a>Remarks

Версия по умолчанию автоматически вызывается конструктором вашего производной класса.

Если ваш класс является сериализируемым (он включает IMPLEMENT_SERIAL макрос), то в декларации класса должен быть конструктор по умолчанию (конструктор без аргументов). Если вам не нужен конструктор по умолчанию, объявите частный или защищенный "пустой" конструктор. Для получения дополнительной информации [см.](../../mfc/using-cobject.md)

Стандартный конструктор копирования класса «СИ» по умолчанию выполняет копию по составу. Наличие конвейера `CObject` частной копии гарантирует сообщение об ошибке компилятора, если конструктор копирования вашего класса необходим, но недоступен. Поэтому необходимо предоставить конструктор копий, если вашему классу требуется эта возможность.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` в примерах. `CObject`

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>Кобъект::D

Сбрасывает содержимое объекта на объект [CDumpContext.](../../mfc/reference/cdumpcontext-class.md)

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
Контекст диагностической свалки для `afxDump`сброса, как правило.

### <a name="remarks"></a>Remarks

Когда вы пишете свой собственный `Dump` класс, вы должны переопределить функцию для предоставления диагностических услуг для себя и других пользователей вашего класса. `Dump` Переивереобычное `Dump` обычно вызывает функцию своего базового класса, прежде чем печатать данные, уникальные для производного класса. `CObject::Dump`печатает название класса, если `IMPLEMENT_DYNAMIC` ваш класс использует IMPLEMENT_SERIAL макрос.

> [!NOTE]
> Функция `Dump` не должна печатать новый символ в конце его вывода.

`Dump`звонки имеют смысл только в версии Debug библиотеки класса Microsoft Foundation. Вы должны скобки вызовов, функции деклараций и функции реализации с **#ifdef _DEBUG** /  `#endif` заявления для условной компиляции.

Поскольку `Dump` функция const является **конст-функцией,** вам не разрешается изменять состояние объекта во время сброса.

Оператор [вставки CDumpContext (<<)](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызывает при `Dump` вставке `CObject` указателя.

`Dump`разрешает только "ациклический" сброс предметов. Например, можно сбросить список объектов, но если одним из объектов является сам список, вы в конечном итоге переполните стек.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>Объект::GetRuntimeClass

Возвращает `CRuntimeClass` структуру, соответствующую классу этого объекта.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) соответствующую классу этого объекта; никогда не **NULL**.

### <a name="remarks"></a>Remarks

Существует одна `CRuntimeClass` структура `CObject`для каждого -производного класса. Члены структуры являются следующими:

- **LPCSTR m_lpszClassName** Строка с нулевым завершением, содержащая имя класса ASCII.

- **m_nObjectSize** Размер объекта, в байтах. Если у объекта есть члены данных, которые указывают на выделенную память, размер этой памяти не включен.

- **UINT m_wSchema** Число схем ( - 1 для несерийных классов). Ознакомьтесь с IMPLEMENT_SERIAL макросом для описания числа схем. [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)

- **CObject\* (PASCAL\* m_pfnCreateObject)( )** Функция указатель на конструктор по умолчанию, который создает объект вашего класса (действительно только если класс поддерживает динамическое создание; в противном случае, возвращает **NULL**).

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass)( ( (** Если ваше приложение динамически связано с версией AFXDLL MFC, указатель на функцию, которая возвращает `CRuntimeClass` структуру базового класса.

- **CRuntimeClass\* m_pBaseClass** Если ваше приложение статически связано с `CRuntimeClass` MFC, указатель на структуру базового класса.

Эта функция требует использования [IMPLEMENT_DYNAMIC,](run-time-object-model-services.md#implement_dynamic) [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макроса в реализации класса. В противном случае вы получите неправильные результаты.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>Объект::IsKindOf

Тестирует отношение этого объекта к данному классу.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Параметры

*pClass*<br/>
Указатель на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанную с классом, полученным в вашем `CObject`классе.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект соответствует классу; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция тестирует *pClass,* чтобы увидеть, если (1) это объект указанного класса или (2) это объект класса, полученный из указанного класса. Эта функция работает только для классов, заявленных с [DECLARE_DYNAMIC,](run-time-object-model-services.md#declare_dynamic) [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макросом.

Не используйте эту функцию широко, потому что она побеждает функцию полиморфизма СЗ. Вместо этого используйте виртуальные функции.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>CObject::IsSerializable

Тестирует, имеет ли этот объект право на сериализацию.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если этот объект может быть сериализован; в противном случае 0.

### <a name="remarks"></a>Remarks

Для того чтобы класс был сериализируемым, его декларация должна содержать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос, а реализация должна содержать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.

> [!NOTE]
> Не перекрывайте эту функцию.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>CObject::оператор удалить

Для версии выпуска библиотеки оператор **удаляет** высвобожденную память, выделенную оператором, **новую.**

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

В версии Debug **оператор удаляет** участие в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

Если вы используете строку кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из ваших реализаций в . Файл CPP, затем будет использоваться третья версия **удаления,** хранение имени файла и номера строки в выделенном блоке для последующей отчетности. Вам не придется беспокоиться о поставке дополнительных параметров; макрозаботится о том, что для вас.

Даже если вы не используете DEBUG_NEW в режиме Debug, вы все равно получаете обнаружение утечки, но без описанной выше отчетов о номере строки исходного файла.

Если вы переопределяете **новых** операторов и **удаляете,** вы лишаетесь этой диагностической возможности.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` в примерах. `CObject`

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>CObject::оператор новый

Для версии выпуска библиотеки оператор **новый** выполняет оптимальное `malloc`распределение памяти таким же образом, как .

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Remarks

В версии Debug оператор **участвует** в схеме мониторинга распределения, предназначенной для обнаружения утечек памяти.

Если вы используете строку кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из ваших реализаций в . Файл CPP, затем будет использоваться вторая версия **новой,** хранящее имя файла и номер строки в выделенном блоке для последующей отчетности. Вам не придется беспокоиться о поставке дополнительных параметров; макрозаботится о том, что для вас.

Даже если вы не используете DEBUG_NEW в режиме Debug, вы все равно получаете обнаружение утечки, но без описанной выше отчетов о номере строки исходного файла.

> [!NOTE]
> Если вы переопределяете этого оператора, вы также должны переопределить **удаление.** Не используйте стандартную функцию библиотеки. `_new_handler`

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` в примерах. `CObject`

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>CObject::Serialize

Считывает этот объект из архива или записывает в него.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Объект `CArchive` для сериализации в или из.

### <a name="remarks"></a>Remarks

Вы должны `Serialize` переопределить для каждого класса, который вы собираетесь сериализовать. `Serialize` Переивергемый `Serialize` должен сначала вызвать функцию своего базового класса.

Вы также должны использовать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос в декларации класса, и вы должны использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации.

Используйте [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) или [CArchive::Istoring,](../../mfc/reference/carchive-class.md#isstoring) чтобы определить, является ли архив загрузкой или хранением.

`Serialize`называется [CArchive:ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связаны с оператором `CArchive` вставки () ** < **и оператором экстракции (). **>>**

Для примеров сериализации [Serialization: Serializing an Object](../../mfc/serialization-serializing-an-object.md)см.

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех `CObject` примерах.

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
