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
ms.openlocfilehash: 515c4e90ee6ab77a6c7c1ae108393ea1aafb7c17
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304071"
---
# <a name="cobject-class"></a>Класс CObject

Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Члены

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CObject::CObject](#cobject)|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CObject::AssertValid](#assertvalid)|Проверяет целостность этого объекта.|
|[CObject::Dump](#dump)|Создает дамп диагностики этого объекта.|
|[CObject::GetRuntimeClass](#getruntimeclass)|Возвращает `CRuntimeClass` структуры, соответствующий классу управляющего объекта.|
|[CObject::IsKindOf](#iskindof)|Проверяет связь этого объекта с указанным классом.|
|[CObject::IsSerializable](#isserializable)|Проверяет, является ли этот объект может быть сериализован.|
|[CObject::Serialize](#serialize)|Загружает и сохраняет объект в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[Удалить CObject::operator](#operator_delete)|Специальные **удалить** оператор.|
|[Новый CObject::operator](#operator_new)|Специальные **новый** оператор.|

## <a name="remarks"></a>Примечания

Он служит в качестве корня не только для библиотеки классов, такие как `CFile` и `CObList`, но также для классов, которые были написаны. `CObject` предоставляет основные службы, включая

- Поддержка сериализации

- Сведения о классе среды выполнения

- Диагностические выходные данные объекта

- Совместимости с классами коллекцию

Обратите внимание, что `CObject` не поддерживает множественное наследование. Производных классах, может иметь только один `CObject` базового класса и `CObject` должен быть крайнее левое положение в иерархии. Допускается, однако чтобы структуры и не- `CObject`-производные классы в ветвях справа множественного наследования.

Вы получаете преимущества от `CObject` наследования, если вы используете некоторые необязательные макросов в реализацию класса и объявления.

Макросы первого уровня, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), во время выполнения доступ к имени класса и его положение в иерархии. Это, в свою очередь, позволяет значимые диагностические формирование дампа.

Макросы второго уровня, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), включают все функции макросы первого уровня, а также облегчают объекта «упорядочивается» и обратно «архив».

Сведения о наследование Microsoft Foundation classes и классы C++, вообще говоря и с помощью `CObject`, см. в разделе [использование CObject](../../mfc/using-cobject.md) и [сериализации](../../mfc/serialization-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CObject`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="assertvalid"></a>  CObject::AssertValid

Проверяет целостность этого объекта.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Примечания

`AssertValid` выполняет проверку допустимости для данного объекта, проверяя его внутреннее состояние. В отладочной версии библиотеки `AssertValid` могут утверждать и таким образом завершить программу с сообщением, которое содержит номер строки и имя файла, где Сбой утверждения.

При написании собственного класса, необходимо переопределить `AssertValid` функция для предоставления службы диагностики для себя и других пользователей вашего класса. Переопределенный `AssertValid` обычно вызывает `AssertValid` функции базового класса перед проверкой данных членов, уникальных для производного класса.

Так как `AssertValid` — **const** функции, нельзя изменить состояние объекта во время теста. Производный класс `AssertValid` функции, не должны вызывать исключения, но вместо этого следует assert ли при обнаружении недопустимого объекта данных.

Определение «действия» зависит от класса объекта. Как правило функции необходимо выполнить «неполная проверку». То есть если объект содержит указатели на другие объекты, он должен проверить ли указатели не равны null, однако не следует выполнять проверку объектов, на который ссылается указатели допустимости.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Еще один пример см. в разделе [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).

##  <a name="cobject"></a>  CObject::CObject

Эти функции представляют собой стандартный `CObject` конструкторы.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Параметры

*objectSrc*<br/>
Ссылка на другой `CObject`

### <a name="remarks"></a>Примечания

Версия по умолчанию автоматически вызывается конструктором производного класса.

Если ваш класс может быть сериализован (оно включает IMPLEMENT_SERIAL-макрос), а затем должен иметь конструктор по умолчанию (конструктор без аргументов) в объявлении класса. Если вам не нужен конструктор по умолчанию, объявить закрытый или защищенный конструктор «empty». Дополнительные сведения см. в разделе [использование CObject](../../mfc/using-cobject.md).

Конструктор копии класса standard C++ по умолчанию выполняется копирование члена, члена. Наличие закрытого `CObject` конструктор копии гарантирует сообщение об ошибке компилятора, если конструктор копии класса необходимые, но не доступна. Если ваш класс требует эту возможность нужно предоставить конструктор копии.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

##  <a name="dump"></a>  CObject::Dump

Выводит содержимое объекта к [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объекта.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Диагностический дамп контекст для создания дампа, обычно `afxDump`.

### <a name="remarks"></a>Примечания

При написании собственного класса, необходимо переопределить `Dump` функция для предоставления службы диагностики для себя и других пользователей вашего класса. Переопределенный `Dump` обычно вызывает `Dump` функции базового класса перед печатью данных членов, уникальных для производного класса. `CObject::Dump` Выводит имя класса, если ваш класс использует `IMPLEMENT_DYNAMIC` или IMPLEMENT_SERIAL-макрос.

> [!NOTE]
>  Ваш `Dump` функции не следует печатать знак новой строки в конце его выходные данные.

`Dump` вызовы смысл только в отладочной версии библиотеки Microsoft Foundation Class. Следует обозначают вызовы, объявления функций и реализации функций с **#ifdef _DEBUG** /  `#endif` инструкций для условной компиляции.

Так как `Dump` — **const** функции, нельзя изменить состояние объекта во время дампа.

[CDumpContext вставки (<<) оператор](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызовы `Dump` при `CObject` вставляется указатель.

`Dump` Разрешает только «ациклический» создания дампа объектов. Можно сделать дамп списка объектов, например, но если один из объектов является сам список, можно будет в конечном счете приводят к переполнению стека.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass

Возвращает `CRuntimeClass` структуры, соответствующий классу управляющего объекта.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) соответствующий класс этого объекта; структуру никогда не **NULL**.

### <a name="remarks"></a>Примечания

Имеется один `CRuntimeClass` структуры для каждого `CObject`-производного класса. Далее приведены элементы структуры.

- **LPCSTR m_lpszClassName** заканчивающуюся нулем строку, содержащую имя класса ASCII.

- **int m_nObjectSize** размер объекта в байтах. Если объект имеет данные-члены, указывающими на выделенную память, объем памяти не включается.

- **Целое число без знака m_wSchema** номер схемы (-1 для классов несериализуемый). См. в разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос описание номер схемы.

- **CObject\* (PASCAL\* m_pfnCreateObject) ()** указатель на функцию в конструктор по умолчанию, который создает объект класса (допустимым только в том случае, если класс поддерживает динамическое создание; в противном случае возвращает **NULL** ).

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** Если приложение динамически связан с версии AFXDLL MFC, указатель на функцию, которая возвращает `CRuntimeClass` структуру базового класса.

- **CRuntimeClass\* m_pBaseClass** Если приложение статически компонуемые с MFC, указатель на `CRuntimeClass` структуру базового класса.

Эта функция требует использования [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализацию класса. В противном случае будет получать неправильные результаты.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

##  <a name="iskindof"></a>  CObject::IsKindOf

Проверяет связь этого объекта с указанным классом.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Параметры

*pClass*<br/>
Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры, связанный с вашей `CObject`-производного класса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект соответствует классу; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция проверяет *pClass* (1) это объект указанного класса или (2) это объект класса, производного от указанного класса. Эта функция работает только для классов, объявленных с [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.

Не используйте эту функцию широко, поскольку он сводит на нет функцию полиморфизм C++. Вместо этого используйте виртуальные функции.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

##  <a name="isserializable"></a>  CObject::IsSerializable

Проверяет, является ли этот объект для сериализации.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот объект может быть сериализован; в противном случае 0.

### <a name="remarks"></a>Примечания

Класс может быть сериализуемым, его объявление должно содержать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) должен содержать макрос и реализацию [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.

> [!NOTE]
>  Эта функция не переопределяется.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

##  <a name="operator_delete"></a>  Удалить CObject::operator

Версии библиотеки оператор **удалить** освобождает память, выделенную оператором **новый**.

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

### <a name="remarks"></a>Примечания

В отладочной версии оператор **удалить** участвует в схему распределения мониторинга, предназначенная для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из ваших реализаций в. Затем файл CPP третьей версии **удалить** будет использоваться, сохранение файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении лишние параметры; макрос берет на себя, для вас.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете обнаружения утечек памяти, но без отчетов номер строки файла исходного кода описано выше.

При переопределении операторов **новый** и **удалить**, можно сделать его непригодным этой возможности диагностики.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

##  <a name="operator_new"></a>  Новый CObject::operator

Версии библиотеки оператор **новый** выполняет в так же, как выделение памяти оптимальной `malloc`.

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Примечания

В отладочной версии оператор **новый** участвует в схему распределения мониторинга, предназначенная для обнаружения утечек памяти.

При использовании строки кода

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

перед любой из ваших реализаций в. Затем файл CPP вторую версию **новый** будет использоваться, сохранение файла и номер строки в выделенном блоке для последующего создания отчетов. Вам не нужно беспокоиться о предоставлении лишние параметры; макрос берет на себя, для вас.

Даже если вы не используете DEBUG_NEW в режиме отладки, вы по-прежнему получаете обнаружения утечек памяти, но без отчетов номер строки файла исходного кода описано выше.

> [!NOTE]
>  Если вы Переопределите этот оператор, необходимо также переопределить **удалить**. Не используйте стандартную библиотеку `_new_handler` функции.

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

##  <a name="serialize"></a>  CObject::Serialize

Считывает этот объект из архива или записывает в него.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Объект `CArchive` сериализуемый с клиента или на объект.

### <a name="remarks"></a>Примечания

Необходимо переопределить `Serialize` для каждого класса, который нужно сериализовать. Переопределенный `Serialize` необходимо сначала вызвать `Serialize` функции базового класса.

Необходимо также использовать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос в объявлении класса и необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации.

Используйте [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) или [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) для определения загрузки или сохранения архива.

`Serialize` вызывается [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связаны с `CArchive` оператор вставки ( **< \<**) и оператор извлечения ( **>>**).

Примеры сериализации см. в статье [сериализации: Сериализация объекта](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
