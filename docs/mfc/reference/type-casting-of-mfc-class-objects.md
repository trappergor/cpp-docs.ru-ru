---
title: Приведение типов объектов классов MFC типов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f459f1cad1b863f0c96e9c885fd2c54831d6b6e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382444"
---
# <a name="type-casting-of-mfc-class-objects"></a>Приведение типов объектов классов MFC

Макросы приведения типов позволяют привести заданный указатель на указатель на объект определенного класса, с или без проверки, что приведение является допустимым.

В следующей таблице перечислены макросы MFC тип приведения.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Макросы, приведение указателей на объекты классов MFC

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Преобразует указатель на указатель на объект класса при проверке того, если приведение является допустимым.|
|[STATIC_DOWNCAST](#static_downcast)|Приведение указателя на объект из одного класса в указатель связанный тип. В отладочной сборке, вызывает УТВЕРЖДЕНИЕ, если объект не является «вида» тип объекта.|

##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST

Предоставляет удобный способ выполнить приведение указателя на указатель на объект класса при проверке того, если приведение является допустимым.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Параметры

*class*<br/>
Имя класса.

*pointer*<br/>
Указатель на быть приведен к указателю на объект типа *класс*.

### <a name="remarks"></a>Примечания

Преобразует макрос *указатель* параметр в указатель на объект *класс* тип параметра.

Если объект, который ссылается указатель «вида» идентифицируемый класс макрос возвращает соответствующий указатель. Если это не юридические приведения к типу, макрос возвращает значение NULL.

##  <a name="static_downcast"></a>  STATIC_DOWNCAST

Приведения *pobject* в указатель на *class_name* объекта.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса, для которого выполняется приведение к.

*pObject*<br/>
Указатель на быть приведен к указателю на *class_name* объекта.

### <a name="remarks"></a>Примечания

*pObject* должен иметь значение NULL или указывает на объект класса, который является производным непосредственно или косвенно, из *class_name*. При построении приложения с помощью символа препроцессора _DEBUG определен макрос ASSERT Если *pobject* не равно NULL, или если он указывает на объект, который не является «вида» указанный в класс *class_name*параметр (см. в разделе [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). В не - **_DEBUG** построений, макрос выполняет преобразование без проверки типа.

Класс, указанный в *class_name* параметр должен быть производным от `CObject` и необходимо использовать DECLARE_DYNAMIC и IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE, или DECLARE_SERIAL и IMPLEMENT_ ПОСЛЕДОВАТЕЛЬНЫЙ макросы, как описано в статье [класс CObject: наследование класса от CObject](../../mfc/deriving-a-class-from-cobject.md).

Например, может привести указатель на `CMyDoc`, который называется `pMyDoc`, указатель на `CDocument` с помощью следующего выражения:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Если `pMyDoc` не указывает на объект, производный прямо или косвенно от `CDocument`, макрос будет УТВЕРЖДАТЬ.

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
