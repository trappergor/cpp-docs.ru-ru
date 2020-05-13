---
title: Класс _com_ptr_t
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: eeaab22ded537cbbb211a79596b8383251af3ab7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189912"
---
# <a name="_com_ptr_t-class"></a>Класс _com_ptr_t

**Блок, относящийся только к системам Microsoft**

Объект **_com_ptr_t** инкапсулирует указатель на интерфейс COM и называется "смарт-указателем". Этот класс шаблона управляет выделением и освобождением ресурсов с помощью вызовов функций к `IUnknown` функциям-членам: `QueryInterface`, `AddRef`и `Release`.

Ссылка на интеллектуальный указатель обычно осуществляется с помощью определения typedef, предоставляемого макросом _COM_SMARTPTR_TYPEDEF. Этот макрос принимает имя интерфейса и IID и объявляет специализацию **_com_ptr_t** с именем интерфейса и суффиксом `Ptr`. Пример:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

объявляет `IMyInterfacePtr`специализации **_com_ptr_t** .

Набор [шаблонов функций](../cpp/relational-function-templates.md), не входящих в этот класс шаблона, поддерживает сравнение со смарт-указателем в правой части оператора сравнения.

### <a name="construction"></a>Строительство

|||
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Конструирует объект **_com_ptr_t** .|

### <a name="low-level-operations"></a>Низкоуровневые операции

|||
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|Вызывает функцию члена `AddRef` `IUnknown` в инкапсулированном указателе интерфейса.|
|[Присоединить](../cpp/com-ptr-t-attach.md)|Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Создает новый экземпляр объекта с заданным `CLSID` или `ProgID`.|
|[Отсоединить](../cpp/com-ptr-t-detach.md)|Извлекает и возвращает инкапсулированный указатель на интерфейс.|
|[жетактивеобжект](../cpp/com-ptr-t-getactiveobject.md)|Присоединяется к существующему экземпляру объекта, заданному `CLSID` или `ProgID`.|
|[жетинтерфацептр](../cpp/com-ptr-t-getinterfaceptr.md)|Возвращает инкапсулированный указатель на интерфейс.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Вызывает функцию члена `QueryInterface` `IUnknown` в инкапсулированном указателе интерфейса.|
|[Выпуск](../cpp/com-ptr-t-release.md)|Вызывает функцию члена `Release` `IUnknown` в инкапсулированном указателе интерфейса.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](../cpp/com-ptr-t-operator-equal.md)|Присваивает новое значение существующему объекту **_com_ptr_t** .|
|[операторы = =,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Сравнивают объект интеллектуального указателя с другим интеллектуальным указателем, необработанным указателем на интерфейс или значением NULL.|
|[Средства извлечения](../cpp/com-ptr-t-extractors.md)|Извлекают инкапсулированный указатель на COM-интерфейс.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<comip. h >

**Lib:** комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t является собственным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>См. также раздел

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)
