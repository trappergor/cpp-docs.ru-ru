---
title: Службы модели объекта во время выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6fb948efd63a8392661cc38a80393bc90d5e694
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396472"
---
# <a name="run-time-object-model-services"></a>Службы модели объекта во время выполнения

Классы [CObject](../../mfc/reference/cobject-class.md) и [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) инкапсулировать несколько служб объектов, включая доступ к сведениям о классе среды выполнения, сериализации и динамическое создание объектов. Все классы, производные от `CObject` наследуют эти функциональные возможности.

Доступ к сведениям о классе во время выполнения позволяет определить сведения о классе объекта во время выполнения. Возможность определения класса объекта во время выполнения полезно в тех случаях, когда требуется дополнительный проверку типов аргументов функции, и когда необходимо написать специальный код, на основе класса объекта. Сведения о классе среды выполнения не поддерживается языком C++.

Сериализацией называется процесс записи или чтения содержимого объекта, в или из файла. Можно использовать сериализацию для хранения содержимого этого объекта, даже после выхода из приложения. Объект затем может быть прочитан из файла, при перезапуске приложения. Такие объекты данных, называются «постоянных».

Динамическое создание объектов позволяет создать объект указанного класса во время выполнения. Например документов, представления и объекты кадров должен поддерживать динамическое создание так, как платформа должна создавать их динамически.

Ниже перечислены макросы MFC, которые поддерживают сведения о классе среды выполнения, сериализации и динамическое создание.

Дополнительные сведения об этих служб объектов времени выполнения и сериализации см. в статье [класс CObject: доступ к сведениям о классе среды выполнения](../../mfc/accessing-run-time-class-information.md).

### <a name="run-time-object-model-services-macros"></a>Макросы служб времени выполнения объектной модели



|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|Разрешает доступ к сведения о классе среды выполнения (необходимо использовать в объявлении класса).|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Обеспечивает динамическое создание и доступ к сведениям о классе среды выполнения (необходимо использовать в объявлении класса).|
|[DECLARE_SERIAL](#declare_serial)|Позволяет сериализацию и доступ к сведениям о классе среды выполнения (необходимо использовать в объявлении класса).|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Разрешает доступ к сведения о классе среды выполнения (необходимо использовать в реализации класса).|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Обеспечивает динамическое создание и доступ к сведениям о времени выполнения (необходимо использовать в реализации класса).|
|[IMPLEMENT_SERIAL](#implement_serial)|Позволяет сериализацию и доступ к сведениям о классе среды выполнения (необходимо использовать в реализации класса).|
|[RUNTIME_CLASS](#runtime_class)|Возвращает `CRuntimeClass` структуры, соответствующий именованный класс.|


OLE часто требуется динамическое создание объектов во время выполнения. Например приложения сервера OLE должен иметь возможность динамически создавать элементы OLE в ответ на запрос от клиента. Аналогичным образом сервер автоматизации, необходима возможность создавать элементы в ответ на запросы от клиентов автоматизации.

Библиотеки Microsoft Foundation Class предоставляет два макроса конкретных OLE.

### <a name="dynamic-creation-of-ole-objects"></a>Динамическое создание объектов OLE








|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Определяет, реализует ли библиотеки стандартных элементов управления указанный API.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Определяет, реализует ли библиотеки стандартных элементов управления указанный API.|
|[DECLARE_OLECREATE](#declare_olecreate)|Позволяет объектам для создания с помощью OLE-автоматизации.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Объявляет `GetUserTypeNameID` и `GetMiscStatus` функции-члены класса элемента управления.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Объявляет, что элемент управления OLE предоставляет список страниц свойств для отображения его свойств.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Позволяет объектам создаваться системой OLE.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Реализует `GetUserTypeNameID` и `GetMiscStatus` функции-члены класса элемента управления.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Либо этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должен присутствовать в файле реализации для любого класса, который использует `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS

Определяет, реализует ли библиотеки стандартных элементов управления указанный API.

### <a name="syntax"></a>Синтаксис

  ```
AFX_COMCTL32_IF_EXISTS(  proc );
```
### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя функции или указывает порядковое значение функции. Если этот параметр имеет порядковый номер, он должен быть в младшее слово; старшее слово должно равняться нулю. Этот параметр должен быть в формате Юникод.

### <a name="remarks"></a>Примечания

Используйте этот макрос для определения ли библиотеки стандартных элементов управления функция определяемое *proc* (вместо вызова метода [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212).

### <a name="requirements"></a>Требования

afxcomctl32.h, afxcomctl32.inl

### <a name="see-also"></a>См. также

[Изоляция библиотеки общих элементов управления MFC](../isolation-of-the-mfc-common-controls-library.md)<br/>
[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)

## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2

Определяет, реализует ли библиотеки стандартных элементов управления указанный API (это версия Юникода [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).

### <a name="syntax"></a>Синтаксис

```
AFX_COMCTL32_IF_EXISTS2( proc );
```
### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя функции или указывает порядковое значение функции. Если этот параметр имеет порядковый номер, он должен быть в младшее слово; старшее слово должно равняться нулю. Этот параметр должен быть в формате Юникод.

### <a name="remarks"></a>Примечания

Используйте этот макрос для определения ли библиотеки стандартных элементов управления функция определяемое *proc* (вместо вызова метода [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212). Этот макрос версия Юникода AFX_COMCTL32_IF_EXISTS.

### <a name="requirements"></a>Требования

afxcomctl32.h, afxcomctl32.inl

### <a name="see-also"></a>См. также

[Изоляция библиотеки общих элементов управления MFC](../isolation-of-the-mfc-common-controls-library.md)<br/>
[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC

Добавлена возможность доступа к информации времени выполнения о класс объекта, при наследовании от класса `CObject`.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Примечания

Добавьте DECLARE_DYNAMIC-макрос модуль заголовка (.h) для класса, а затем включить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.

При использовании ДИНАМИЧЕСКИХ DECLARE_ и IMPLEMENT_DYNAMIC макросы, как описано, можно затем использовать макроса RUNTIME_CLASS и `CObject::IsKindOf` функцию, чтобы определить класс объектов во время выполнения.

Если DECLARE_DYNAMIC включен в объявление класса, IMPLEMENT_DYNAMIC должны быть включены в реализацию класса.

Дополнительные сведения о DECLARE_DYNAMIC-макрос, см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

См. в примере [IMPLEMENT_DYNAMIC](#implement_dynamic).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE

Позволяет объектам из `CObject`-производным классам создаваться динамически во время выполнения.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Примечания

Инфраструктура использует эту возможность для динамического создания новых объектов. Например новое представление создается при открытии документа. Документов, представления и классы фрейма должен поддерживать динамическое создание, так как платформа должна создавать их динамически.

Добавление declare_dyncreate-макрос в модуле .h для класса, а затем включить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.

Если DECLARE_DYNCREATE включен в объявление класса, IMPLEMENT_DYNCREATE должны быть включены в реализацию класса.

Дополнительные сведения о declare_dyncreate-макрос, см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

> [!NOTE]
>  Declare_dyncreate-макрос включает в себя все функции DECLARE_DYNAMIC.

### <a name="example"></a>Пример

См. в примере [IMPLEMENT_DYNCREATE](#implement_dyncreate).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h


## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE

Объявляет `GetUserTypeNameID` и `GetMiscStatus` функции-члены класса элемента управления.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name )
```
### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

### <a name="remarks"></a>Примечания

`GetUserTypeNameID` и `GetMiscStatus` являются чистые виртуальные функции, объявленные в `COleControl`. Так как эти функции являются чистые виртуальные, они должны быть переопределены в классе элемента управления. В дополнение к DECLARE_OLECTLTYPE необходимо добавить implement_olectltype-макрос к объявлению класса элемента управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

### <a name="see-also"></a>См. также

[IMPLEMENT_OLECTLTYPE](#implement_olectltype)


## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS

Объявляет, что элемент управления OLE предоставляет список страниц свойств для отображения его свойств.

### <a name="syntax"></a>Синтаксис

```
DECLARE_PROPPAGEIDS( class_name )
```
### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, которому принадлежит на страницах свойств.

### <a name="remarks"></a>Примечания

Используйте `DECLARE_PROPPAGEIDS` макрос в конце объявления класса. Затем в CPP-файле, который определяет функции-члены класса, используйте `BEGIN_PROPPAGEIDS` макрос, макрос записи для каждой из страниц свойств элемента управления и `END_PROPPAGEIDS` макрос для объявления в конец списка страницы свойств.

Дополнительные сведения о страницах свойств см. в статье [элементы управления ActiveX: страницы свойств](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

### <a name="see-also"></a>См. также

[BEGIN_PROPPAGEIDS](#begin_proppageids)<br/>
[END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>  DECLARE_SERIAL

Создает заголовок код C++, необходимые для `CObject`-производный класс, который может быть сериализован.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Примечания

Сериализацией называется процесс записи или чтению содержимого объект и из файла.

Используйте declare_serial-макрос в модуле .h и затем включить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.

Если DECLARE_SERIAL включен в объявление класса, IMPLEMENT_SERIAL должны быть включены в реализацию класса.

Declare_serial-макрос содержит все функции DECLARE_DYNAMIC и DECLARE_DYNCREATE.

Макрос AFX_API можно использовать для автоматического экспорта `CArchive` оператор извлечения для классов, которые используются макросы DECLARE_SERIAL и IMPLEMENT_SERIAL. Квадратная скобка объявления класса (расположен в h-файле) следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Дополнительные сведения о declare_serial-макрос, см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC

Создает код C++, необходимые для динамического `CObject`-производного класса во время выполнения доступ к имени класса и положение в иерархии.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Имя базового класса.

### <a name="remarks"></a>Примечания

Использовать implement_dynamic-макрос в .cpp модуля, а затем свяжите результирующий код объекта только один раз.

Дополнительные сведения см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE

Позволяет объектам из `CObject`-производные классы, динамически создаваемых при запуске время при использовании declare_dyncreate-макрос.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Фактическое имя базового класса.

### <a name="remarks"></a>Примечания

Инфраструктура использует эту возможность для создания новых объектов динамически, например, при считывании объекта с диска во время сериализации. Добавьте implement_dyncreate-макрос в файле реализации класса. Дополнительные сведения см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

Если вы используете макросы DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE, затем можно использовать макроса RUNTIME_CLASS и `CObject::IsKindOf` функция-член для определения класса объектов во время выполнения.

Если DECLARE_DYNCREATE включен в объявление класса, IMPLEMENT_DYNCREATE должны быть включены в реализацию класса.

Обратите внимание на то, что это определение макроса, вызовет конструктор по умолчанию для класса. Если нетривиальным конструктором явно реализован классом, он должен также явно реализовать конструктор по умолчанию. Конструктор по умолчанию можно добавить в класс **частного** или **защищенные** член разделах, чтобы запретить его вызов из за пределами реализация класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS

Либо этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должен присутствовать в файле реализации для любого класса, который использует DECLARE_OLECREATE.

### <a name="syntax"></a>Синтаксис

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)

```
### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*параметр external_name*<br/>
Имя объекта, другим приложениям (заключенная в кавычки).

*nFlags*<br/>
Содержит один или несколько из следующих флагов:

   - `afxRegInsertable` Позволяет элементу управления отображаются в диалоговом окне Вставка объекта для объектов OLE.
   - `afxRegApartmentThreading` Задает модель потоков в реестре ThreadingModel = подразделения.
   - `afxRegFreeThreading` Задает модель потоков в реестре ThreadingModel = Free.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/desktop/com/inprocserver32) in the Windows SDK for more information on threading model registration.

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* компоненты класса CLSID.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Если вы используете IMPLEMENT_OLECREATE_FLAGS, можно указать какие потоковой модели, поддерживаемые объектом с помощью *nFlags* параметра. Если необходима поддержка только одного treading модель, используйте IMPLEMENT_OLECREATE.

Внешнее имя является идентификатором для других приложений. Клиентским приложениям использовать внешнее имя для запроса объекта данного класса из сервера автоматизации.

Идентификатор класса OLE — это уникальный 128-разрядный идентификатор, для объекта. Он состоит из одной **long**, два **WORD**s и восемь **БАЙТОВ**s, представленные как *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастера мастер приложения и код создает уникальные идентификаторы класса OLE при необходимости.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[DECLARE_OLECREATE](#declare_olecreate)<br/>
[Раздел CLSID](/windows/desktop/com/clsid-key-hklm)


## <a name="implement_olecreate"></a> IMPLEMENT_OLECTLTYPE

Реализует `GetUserTypeNameID` и `GetMiscStatus` функции-члены класса элемента управления.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```
### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

*idsUserTypeName*<br/>
Идентификатор ресурса строка, содержащая имя внешнего элемента управления.

*dwOleMisc*<br/>
Перечисление, содержащее один или несколько флагов. Дополнительные сведения об этом перечислении см. в разделе [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

В дополнение к IMPLEMENT_OLECTLTYPE необходимо добавить declare_olectltype-макрос к объявлению класса элемента управления.

`GetUserTypeNameID` Функция-член возвращает строку ресурса, которая определяет класса элемента управления. `GetMiscStatus` Возвращает OLEMISC разряда для элемента управления. Это перечисление определяет коллекцию параметров, определяющих различные характеристики вашего элемента управления. Полное описание параметров OLEMISC, см. в разделе [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) в пакете Windows SDK.

> [!NOTE]
>  Параметры по умолчанию, используемые автоматически ActiveX: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, установке OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE и OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL

Создает код C++, необходимые для динамического `CObject`-производного класса во время выполнения доступ к имени класса и положение в иерархии.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Имя базового класса.

*wSchema*<br/>
Целое число без знака «номером версии», будут закодированы в архив, чтобы включить программу десериализации для идентификации и обработки данных, созданных ранее программировать версий. Номер схемы класса не должно быть -1.

### <a name="remarks"></a>Примечания

Использовать IMPLEMENT_SERIAL-макрос в .cpp модуля; Свяжите результирующий код объекта только один раз.

Макрос AFX_API можно использовать для автоматического экспорта `CArchive` оператор извлечения для классов, которые используются макросы DECLARE_SERIAL и IMPLEMENT_SERIAL. Квадратная скобка объявления класса (расположен в h-файле) следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Дополнительные сведения см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="runtime_class"></a>  RUNTIME_CLASS

Возвращает структуру класса среды выполнения от имени класса C++.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса (не заключаются в кавычки).

### <a name="remarks"></a>Примечания

RUNTIME_CLASS возвращает указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структура для класса, указанного параметром *class_name*. Только `CObject`-производные классы, объявленные с DECLARE_DYNAMIC, DECLARE_DYNCREATE или DECLARE_SERIAL возвращает указатели на `CRuntimeClass` структуры.

Дополнительные сведения см. в разделе [разделы по классам CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE

Позволяет объектам из `CCmdTarget`-производные классы для создания с помощью OLE-автоматизации.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Примечания

Этот макрос позволяет другим приложениям с поддержкой OLE создавать объекты этого типа.

Добавьте в модуле .h для класса declare_olecreate-макрос и затем включить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.

Если DECLARE_OLECREATE включен в объявление класса, IMPLEMENT_OLECREATE должны быть включены в реализацию класса. Объявление класса, с помощью DECLARE_OLECREATE необходимо также использовать DECLARE_DYNCREATE или DECLARE_SERIAL.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE

Либо этот макрос или [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) должен присутствовать в файле реализации для любого класса, который использует `DECLARE_OLECREATE`.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*параметр external_name*<br/>
Имя объекта, другим приложениям (заключенная в кавычки).

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* компоненты класса CLSID.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Если вы используете IMPLEMENT_OLECREATE, по умолчанию, вы поддерживает только один потоковой модели. Если вы используете IMPLEMENT_OLECREATE_FLAGS, можно указать какие потоковой модели, поддерживаемые объектом с помощью *nFlags* параметра.

Внешнее имя является идентификатором для других приложений. Клиентским приложениям использовать внешнее имя для запроса объекта данного класса из сервера автоматизации.

Идентификатор класса OLE — это уникальный 128-разрядный идентификатор, для объекта. Он состоит из одной **long**, два **WORD**s и восемь **БАЙТОВ**s, представленные как *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастера мастер приложения и код создает уникальные идентификаторы класса OLE при необходимости.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

