---
title: Класс CObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38c27d2fa0e04770bae69901e1164da84c2186ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cobject-class"></a>CObject-класс
Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObject::AssertValid](#assertvalid)|Проверяет целостность этого объекта.|  
|[CObject::Dump](#dump)|Создает дамп диагностики этого объекта.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Возвращает `CRuntimeClass` структуры, соответствующей класса этого объекта.|  
|[CObject::IsKindOf](#iskindof)|Проверяет связь этого объекта с указанным классом.|  
|[CObject::IsSerializable](#isserializable)|Проверяет, можно ли сериализовать данный объект.|  
|[CObject::Serialize](#serialize)|Загружает и не сохраняет объект из или в архив.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Удаление CObject::operator](#operator_delete)|Специальные **удалить** оператор.|  
|[Новый CObject::operator](#operator_new)|Специальные **новый** оператор.|  
  
## <a name="remarks"></a>Примечания  
 Он служит в качестве корневого не только для классов библиотеки например `CFile` и `CObList`, но также для классов, которые пишутся. `CObject` предоставляет основные службы, включая  
  
-   Поддержка сериализации  
  
-   Сведения о классе во время выполнения  
  
-   Объект выходных данных диагностики  
  
-   Совместимость с классы коллекций  
  
 Обратите внимание, что `CObject` не поддерживает множественное наследование. Производные классы могут иметь только одно `CObject` базового класса и что `CObject` должен быть крайнее левое положение в иерархии. Он является допустимым, однако чтобы структуры и не- `CObject`-производными классами в правом ветвей множественного наследования.  
  
 Вы получаете преимущества от `CObject` наследования при использовании некоторых необязательно макросов в реализацию класса и объявления.  
  
 Макросы первого уровня, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), во время выполнения доступ к имени класса и его положение в иерархии. Это, в свою очередь, позволяет значимые диагностические записи в дамп.  
  
 Макросы второго уровня [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), включает все функции макросов первого уровня, а также облегчают объекта «упорядочивается» и «архив».  
  
 Сведения о производных классов Microsoft Foundation classes и классы C++ в целом и с помощью `CObject`, в разделе [использование CObject](../../mfc/using-cobject.md) и [сериализации](../../mfc/serialization-in-mfc.md).  
  
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
 `AssertValid` выполняет проверку допустимости для этого объекта, проверяя его внутреннее состояние. В отладочной версии библиотеки `AssertValid` могут утверждать и таким образом завершить программу сообщением, содержащим указаны имя файла и номер строки, где Сбой утверждения.  
  
 При написании собственного класса, необходимо переопределить `AssertValid` функции использовать диагностические службы для себя и других пользователей вашего класса. Переопределенный `AssertValid` обычно вызывает `AssertValid` функции базового класса перед проверкой данных членов, уникальных для производного класса.  
  
 Поскольку `AssertValid` — **const** функции, нельзя изменить состояние объекта во время теста. Производный класс `AssertValid` функции не должен выдавать исключения, но вместо этого следует assert ли они обнаружение недопустимого объекта данных.  
  
 Определение «действия», зависит от класса объекта. Как правило функция должна выполнить «неполная проверка». То есть если объект содержит указатели на другие объекты, его следует проверьте ли указатели не являются пустыми, но не следует выполнять проверку на объекты, на который ссылается указатели допустимости.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Еще один пример см. в разделе [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>  CObject::CObject  
 Эти функции являются стандартной `CObject` конструкторы.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *objectSrc*  
 Ссылка на другой `CObject`  
  
### <a name="remarks"></a>Примечания  
 Версия по умолчанию автоматически вызывается конструктор производного класса.  
  
 Если ваш класс может быть сериализован (оно включает `IMPLEMENT_SERIAL` макрос), то в объявлении класса, должен иметь конструктор по умолчанию (конструктор без аргументов). Если не требуется конструктор по умолчанию, объявить закрытый или защищенный конструктор «empty». Дополнительные сведения см. в разделе [использование CObject](../../mfc/using-cobject.md).  
  
 Конструктор копии стандартный класс C++ по умолчанию выполняется копирование члена, члена. Наличие закрытого `CObject` конструктор копии гарантирует сообщение об ошибке компилятора, если конструктор копии класса требуется, но не доступен. Конструктор копии таким образом необходим, если ваш класс требует этой возможности.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>  CObject::Dump  
 Выводит содержимое объекта в [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объекта.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Контекст дампа диагностики для дампа обычно `afxDump`.  
  
### <a name="remarks"></a>Примечания  
 При написании собственного класса, необходимо переопределить `Dump` функции использовать диагностические службы для себя и других пользователей вашего класса. Переопределенный `Dump` обычно вызывает `Dump` функции базового класса перед печатью данных членов, уникальных для производного класса. `CObject::Dump` Выводит имя класса, если ваш класс использует `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` макрос.  
  
> [!NOTE]
>  Ваш `Dump` функции не следует печатать символ перевода строки в конце его выходных данных.  
  
 `Dump` вызовы смысл только в отладочной версии библиотеки классов Microsoft Foundation. Следует квадратная скобка вызовов, объявления функций и реализация функций с **#ifdef _DEBUG** /  `#endif` инструкций для условной компиляции.  
  
 Поскольку `Dump` — **const** функции, нельзя изменить состояние объекта во время дампа.  
  
 [CDumpContext вставки (<<) оператор](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызовы `Dump` при `CObject` вставляется указателя.  
  
 `Dump` Разрешает только «ациклического» создания дампа объектов. Можно сделать дамп списка объектов, к примеру, но если один из объектов является сам список, в конечном итоге будет переполнению стека.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass  
 Возвращает `CRuntimeClass` структуры, соответствующей класса этого объекта.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры, соответствующей этот объект класса, никогда не **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Имеется один `CRuntimeClass` структуры для каждого `CObject`-производного класса. Элементы структуры выглядят следующим образом:  
  
- **LPCSTR m_lpszClassName** нулем строка, содержащая имя класса ASCII.  
  
- **int m_nObjectSize** размер объекта в байтах. Если объект имеет члены данных этой точки выделенную память, объем памяти, не включается.  
  
- **UINT m_wSchema** номер схемы (-1 для классов несериализуемый). В разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос описание номер схемы.  
  
- **CObject\* (PASCAL\* m_pfnCreateObject) ()** указатель на функцию в конструктор по умолчанию, которая создает объект класса (допустимым только в том случае, если класс поддерживает динамическое создание; в противном случае возвращает **значение NULL** ).  
  
- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** Если приложение динамически связан AFXDLL-версия MFC, указатель на функцию, возвращающий `CRuntimeClass` структура базового класса.  
  
- **CRuntimeClass\* m_pBaseClass** Если ваше приложение статически компонуемые с MFC, указатель на `CRuntimeClass` структура базового класса.  
  
 Эта функция требует использования [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализацию класса. В противном случае будет получить неверные результаты.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>  CObject::IsKindOf  
 Проверяет связь этого объекта с указанным классом.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pClass`  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структур, связанных с вашей `CObject`-производного класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект соответствует классу; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция проверяет `pClass` (1) он является объектом указанного класса или (2) он является объектом класса, производного от указанного класса. Эта функция работает только для классов, объявленные с [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.  
  
 Не используйте эту функцию активно, так как он сводит на нет полиморфизм компонент C++. Вместо этого используйте виртуальные функции.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>  CObject::IsSerializable  
 Проверяет, является ли этот объект для сериализации.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот объект может быть сериализован. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Для класса для сериализации, должен содержать объявления [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос и реализация должна содержать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.  
  
> [!NOTE]
>  Эта функция не переопределяется.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>  Удаление CObject::operator  
 Для версии библиотеки оператор **удаление** освобождает память, выделенную оператором **новый**.  
  
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
 В отладочной версии оператор **удалить** участвует в схему распределения наблюдения, предназначенная для обнаружения утечек памяти.  
  
 Если вы используете строку кода  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 перед любым в реализации. Затем файл CPP третьей версии **удалить** будет использоваться, сохранение файла и номер строки в выделенном блоке для последующего создания отчетов. Не нужно беспокоиться о предоставлении лишние параметры; макрос отвечает за вас.  
  
 Даже если вы не используете `DEBUG_NEW` в режиме отладки продолжают возникать обнаружение утечек памяти, но без номер строки исходного файла отчетов описано выше.  
  
 При переопределении операторов **новый** и **удалить**, то во избежание понижения этой возможности диагностики.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>  Новый CObject::operator  
 Для версии библиотеки оператор **новый** выполняет в так же, как выделение памяти оптимальной `malloc`.  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>Примечания  
 В отладочной версии оператор **новый** участвует в схему распределения наблюдения, предназначенная для обнаружения утечек памяти.  
  
 Если вы используете строку кода  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 перед любым в реализации. Затем файл CPP вторая версия **новый** будет использоваться, сохранение файла и номер строки в выделенном блоке для последующего создания отчетов. Не нужно беспокоиться о предоставлении лишние параметры; макрос отвечает за вас.  
  
 Даже если вы не используете `DEBUG_NEW` в режиме отладки продолжают возникать обнаружение утечек памяти, но без номер строки исходного файла отчетов описано выше.  
  
> [!NOTE]
>  Если этот оператор, необходимо также переопределить **удалить**. Не используйте стандартную библиотеку **_new_handler** функции.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>  CObject::Serialize  
 Считывает этот объект из архива или записывает в него.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект для сериализации в.  
  
### <a name="remarks"></a>Примечания  
 Необходимо переопределить `Serialize` для каждого класса, который нужно сериализовать. Переопределенный `Serialize` необходимо сначала вызвать `Serialize` функции базового класса.  
  
 Необходимо также использовать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос в объявлении класса и необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации.  
  
 Используйте [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) или [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) для определения загрузки или хранения архива.  
  
 `Serialize` вызывается методом [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связаны с `CArchive` оператор вставки ( **< \<**) и оператор извлечения ( **>>**).  
  
 Примеры сериализации см. в статье [сериализации: сериализация объекта](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



