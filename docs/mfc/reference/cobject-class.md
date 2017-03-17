---
title: "Класс CObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- base classes, MFC objects
- objects [C++], base class for MFC
- object classes
- CObject class
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d411b9da8618eaac57045a1db05251517422976a
ms.lasthandoff: 02/24/2017

---
# <a name="cobject-class"></a>CObject-класс
Основной базовый класс для всех исключений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObject::AssertValid](#assertvalid)|Проверяет целостность этого объекта.|  
|[CObject::Dump](#dump)|Создает дамп диагностики этого объекта.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Возвращает `CRuntimeClass` структуру соответствующего класса этого объекта.|  
|[CObject::IsKindOf](#iskindof)|Проверяет связь этого объекта с указанным классом.|  
|[CObject::IsSerializable](#isserializable)|Проверяет, можно ли сериализовать данный объект.|  
|[CObject::Serialize](#serialize)|Загружает и хранит объект из или в архив.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Удалить CObject::operator](#operator_delete)|Специальные **удаление** оператор.|  
|[Новый CObject::operator](#operator_new)|Специальные **новый** оператор.|  
  
## <a name="remarks"></a>Примечания  
 Он служит в качестве корня не только для библиотеки классов, такие как `CFile` и `CObList`, но также для классов, которые вы пишете. `CObject`предоставляет основные службы, включая  
  
-   Поддержка сериализации  
  
-   Сведения о классе во время выполнения  
  
-   Объект выходных данных диагностики  
  
-   Совместимость с классы коллекций  
  
 Обратите внимание, что `CObject` не поддерживает множественное наследование. Ваш производные классы могут иметь только один `CObject` базового класса и `CObject` должен быть крайнее левое положение в иерархии. Допускается, однако, иметь структуры и не- `CObject`-производными классами в правом ветвей с множественным наследованием.  
  
 Вы получаете преимущества от `CObject` наследование при использовании некоторых необязательно макросы в реализацию класса и объявления.  
  
 Макросы первого уровня [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) и [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), во время выполнения доступ к имени класса и его положение в иерархии. Это, в свою очередь, позволяет значимые диагностические дампа.  
  
 Макросы второго уровня, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), включает все функции макросов первого уровня, и они дают «сериализуемый объект» и «архивный».  
  
 Сведения о производных классов Microsoft Foundation classes и классы C++ в целом и с помощью `CObject`, в разделе [использование CObject](../../mfc/using-cobject.md) и [сериализации](../../mfc/serialization-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="assertvalid"></a>CObject::AssertValid  
 Проверяет целостность этого объекта.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>Примечания  
 `AssertValid`выполняет проверку действительности для этого объекта путем проверки внутреннего состояния. В отладочной версии библиотеки `AssertValid` могут утверждать и таким образом завершить программу сообщением, содержащим указаны имя файла и номер строки, где ложности.  
  
 При написании собственного класса, необходимо переопределить `AssertValid` функции использовать диагностические службы для себя и других пользователей вашего класса. Переопределенный `AssertValid` обычно вызывает `AssertValid` функции базового класса перед проверкой данных членов, уникальных для производного класса.  
  
 Поскольку `AssertValid` — **const** функции, нельзя изменить состояние объекта во время теста. Производный класс `AssertValid` функции не должен выдавать исключения, но вместо этого следует assert обнаружения недопустимый объект данных.  
  
 Определение «действия» зависит от класса объекта. Как правило функции должен выполнять «неполную проверку». То есть если объект содержит указатели на другие объекты, оно должно проверить ли указатели не равны null, но не следует выполнять проверку объектов, на который ссылается указатели допустимости.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample&#7;](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Еще один пример см. в разделе [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>CObject::CObject  
 Эти функции являются стандартные `CObject` конструкторы.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *objectSrc*  
 Ссылка на другой`CObject`  
  
### <a name="remarks"></a>Примечания  
 Версия по умолчанию автоматически вызывается конструктор производного класса.  
  
 Если класс является сериализуемым (он включает в себя `IMPLEMENT_SERIAL` макрос), то должен иметь конструктор по умолчанию (конструктор без аргументов) в объявлении класса. Если не требуется конструктор по умолчанию, объявить закрытый или защищенный конструктор «empty». Дополнительные сведения см. в разделе [использование CObject](../../mfc/using-cobject.md).  
  
 Стандартный конструктор копии класса C++ по умолчанию выполняется копирование элементов в элемент. Наличие закрытого `CObject` конструктор копии гарантирует сообщение об ошибке компилятора, если конструктор копии класса необходимые, но не доступен. Таким образом, необходимо предоставить конструктор копии Если ваш класс требует этой возможности.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примерах.  
  
 [!code-cpp[NVC_MFCCObjectSample №&8;](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>CObject::Dump  
 Выводит содержимое объекта для [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объекта.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Контекст дампа диагностики для создания дампа, обычно `afxDump`.  
  
### <a name="remarks"></a>Примечания  
 При написании собственного класса, необходимо переопределить `Dump` функции использовать диагностические службы для себя и других пользователей вашего класса. Переопределенный `Dump` обычно вызывает `Dump` функции базового класса перед печатью данных членов, уникальных для производного класса. `CObject::Dump`Выводит имя класса, если класс использует `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` макрос.  
  
> [!NOTE]
>  Ваш `Dump` функции не следует печатать знак новой строки в конце его выходные данные.  
  
 `Dump`вызовы смысл только в отладочной версии библиотеки Microsoft Foundation Class. Следует скобкой вызовы, объявления функций и реализаций функции с **#ifdef _DEBUG** /  `#endif` инструкции для условной компиляции.  
  
 Поскольку `Dump` — **const** функции, нельзя изменить состояние объекта во время дампа.  
  
 [CDumpContext вставки (<)> </)> ](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) вызовов `Dump` при `CObject` вставляется указателя.  
  
 `Dump`Разрешает дамп только «ациклического» объектов. Можно сделать дамп списка объектов, например, но если один из объектов является сам список, в конечном итоге будет переполнению стека.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample №&9;](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>CObject::GetRuntimeClass  
 Возвращает `CRuntimeClass` структуру соответствующего класса этого объекта.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру соответствующего класса этого объекта; никогда не **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Имеется один `CRuntimeClass` структуры для каждого `CObject`-производного класса. Члены структуры выглядят следующим образом:  
  
- **LPCSTR m_lpszClassName** нулем строка, содержащая имя класса ASCII.  
  
- **int m_nObjectSize** размер объекта в байтах. Если объект содержит члены данных, указывающие на выделенную память, объем памяти не включается.  
  
- **UINT m_wSchema** номер схемы (– 1 для классов несериализуемый). В разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос описание схемы номер.  
  
- **CObject\* (PASCAL\* m_pfnCreateObject) ()** указатель на функцию конструктора по умолчанию, создающий объект класса (допустимым только в том случае, если класс поддерживает динамическое создание; в противном случае — возвращает **NULL**).  
  
- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** Если приложение динамически связан AFXDLL-версия MFC, указатель на функцию, возвращающий `CRuntimeClass` структуру базового класса.  
  
- **CRuntimeClass\* m_pBaseClass** Если приложение статически компонуемые с MFC, указатель на `CRuntimeClass` структуру базового класса.  
  
 Эта функция требует использования [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), или [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализацию класса. В противном случае будет получить неверные результаты.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample&#10;](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>CObject::IsKindOf  
 Проверяет связь этого объекта с указанным классом.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pClass`  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры, связанный с вашей `CObject`-производного класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект соответствует классу; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция проверяет `pClass` (1) это объект указанного класса или (2) это объект класса, производного от указанного класса. Эта функция работает только для классов, объявленные с [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.  
  
 Не используйте эту функцию широко, поскольку он сводит на нет функция полиморфизма C++. Вместо этого используйте виртуальные функции.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample&11;](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>CObject::IsSerializable  
 Проверяет, является ли этот объект для сериализации.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот объект может быть сериализован. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Класс может быть сериализуемым, его объявление должно содержать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос и реализации должны содержать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.  
  
> [!NOTE]
>  Эта функция не переопределяется.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample&#12;](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>Удалить CObject::operator  
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
 В отладочной версии оператор **удаление** участвует в схему распределения наблюдения, предназначенная для обнаружения утечек памяти.  
  
 При использовании строки кода  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 перед любым в реализации. Затем файл CPP третьей версии **удаление** будет использоваться, сохранения файла и номер строки в выделенном блоке для последующего создания отчетов. Не нужно беспокоиться о предоставлении дополнительных параметров; макрос берет на себя, для вас.  
  
 Даже если вы не используете `DEBUG_NEW` в режиме отладки, по-прежнему получить обнаружение утечек памяти, но без номер строки исходного файла отчетов описанных выше.  
  
 При переопределении операторы **новый** и **удаление**, можно сделать его непригодным этой возможности диагностики.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примерах.  
  
 [!code-cpp[NVC_MFCCObjectSample&#15;](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>Новый CObject::operator  
 Для версии библиотеки оператор **новый** выполняет так же, как выделение памяти оптимальной `malloc`.  
  
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
  
 При использовании строки кода  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 перед любым в реализации. Затем файл CPP вторая версия **новый** будет использоваться, сохранения файла и номер строки в выделенном блоке для последующего создания отчетов. Не нужно беспокоиться о предоставлении дополнительных параметров; макрос берет на себя, для вас.  
  
 Даже если вы не используете `DEBUG_NEW` в режиме отладки, по-прежнему получить обнаружение утечек памяти, но без номер строки исходного файла отчетов описанных выше.  
  
> [!NOTE]
>  При переопределении этого оператора, необходимо также переопределить **удаление**. Не используйте стандартную библиотеку **_new_handler** функции.  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый в `CObject` примерах.  
  
 [!code-cpp[NVC_MFCCObjectSample №&16;](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>CObject::Serialize  
 Считывает этот объект из архива или записывает в него.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект для сериализации в.  
  
### <a name="remarks"></a>Примечания  
 Необходимо переопределить `Serialize` для каждого класса, который требуется сериализовать. Переопределенный `Serialize` необходимо сначала вызвать `Serialize` функции базового класса.  
  
 Необходимо также использовать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос в объявлении класса и необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации.  
  
 Используйте [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) или [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) для определения загрузки или сохранения архива.  
  
 `Serialize`вызывается методом [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) и [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Эти функции связанные с `CArchive` оператор вставки ( ** < \< **) и оператор извлечения ( ** >> **).  
  
 Примеры сериализации см. в статье [сериализация: сериализация объекта](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех `CObject` примеры.  
  
 [!code-cpp[NVC_MFCCObjectSample&#13;](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




