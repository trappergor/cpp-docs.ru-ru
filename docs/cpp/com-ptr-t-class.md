---
title: Класс _com_ptr_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb343431a52df9fae32bb17f3303738c04385cf5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944220"
---
# <a name="comptrt-class"></a>Класс _com_ptr_t
**Блок, относящийся только к системам Microsoft**  
  
 Объект `_com_ptr_t` инкапсулирует указатель на COM-интерфейс и называется интеллектуальным указателем. Этот класс шаблона управляет выделением и освобождением посредством вызовов функций для ресурсов `IUnknown` функций-членов: `QueryInterface`, `AddRef`, и `Release`.  
  
 Интеллектуальный указатель обычно ссылаются определения typedef, предоставляемого макросом _COM_SMARTPTR_TYPEDEF. Этот макрос имеет имя интерфейса и IID и объявляет специализацию объекта `_com_ptr_t`, используя имя интерфейса и суффикс `Ptr`. Пример:  
  
```cpp 
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 объявляет `_com_ptr_t` специализации `IMyInterfacePtr`.  
  
 Набор [функции шаблонов](../cpp/relational-function-templates.md), не являющихся членами этого шаблона класса, поддерживает сравнение с интеллектуальным указателем в правой части оператора сравнения.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Создает объект `_com_ptr_t`.|  
  
### <a name="low-level-operations"></a>Низкоуровневые операции  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Вызовы `AddRef` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.|  
|[Attach](../cpp/com-ptr-t-attach.md)|Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Создает новый экземпляр объекта, учитывая `CLSID` или `ProgID`.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Извлекает и возвращает инкапсулированный указатель на интерфейс.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Присоединяет к существующему экземпляру объекта, учитывая `CLSID` или `ProgID`.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Возвращает инкапсулированный указатель на интерфейс.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Вызовы `QueryInterface` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.|  
|[Релиз](../cpp/com-ptr-t-release.md)|Вызовы `Release` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../cpp/com-ptr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_com_ptr_t`.|  
|[операторы: ==,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Сравнение объекта интеллектуального указателя с другим интеллектуальным указателем, необработанным указателем на интерфейс, или значение NULL.|  
|[Средства извлечения](../cpp/com-ptr-t-extractors.md)|Извлекают инкапсулированный указатель на COM-интерфейс.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<comip.h >  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (см. в разделе [/Zc: wchar_t (wchar_t — собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Дополнительные сведения)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)