---
title: "Класс _com_ptr_t | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3979a33f095092c5cbaac91793c501e31304a6d4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrt-class"></a>Класс _com_ptr_t
**Блок, относящийся только к системам Майкрософт**  
  
 Объект `_com_ptr_t` инкапсулирует указатель на COM-интерфейс и называется интеллектуальным указателем. Этот класс шаблона управляет выделением и освобождением посредством вызовов функций для ресурсов **IUnknown** функций-членов: `QueryInterface`, `AddRef`, и **выпуска**.  
  
 Интеллектуальный указатель обычно ссылаются определения typedef, предоставляемого **_COM_SMARTPTR_TYPEDEF** макрос. Этот макрос имеет имя интерфейса и IID и объявляет специализацию объекта `_com_ptr_t`, используя имя интерфейса и суффикс `Ptr`. Пример:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 объявляет `_com_ptr_t` специализации **IMyInterfacePtr**.  
  
 Набор [функции шаблонов](../cpp/relational-function-templates.md), не являющихся членами данного шаблона класса поддерживает сравнение с интеллектуальным указателем в правой части оператора сравнения.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Создает объект `_com_ptr_t`.|  
  
### <a name="low-level-operations"></a>Низкоуровневые операции  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Вызовы `AddRef` функцию-член **IUnknown** на инкапсулированный указатель на интерфейс.|  
|[Attach](../cpp/com-ptr-t-attach.md)|Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Создает новый экземпляр объекта, заданного **CLSID** или **ProgID**.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Извлекает и возвращает инкапсулированный указатель на интерфейс.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Присоединяет к существующему экземпляру объекта, заданного **CLSID** или **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Возвращает инкапсулированный указатель на интерфейс.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Вызовы `QueryInterface` функцию-член **IUnknown** на инкапсулированный указатель на интерфейс.|  
|[Релиз](../cpp/com-ptr-t-release.md)|Вызовы **выпуска** функцию-член **IUnknown** на инкапсулированный указатель на интерфейс.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../cpp/com-ptr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_com_ptr_t`.|  
|[операторы ==,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Сравнивают объект интеллектуального указателя с другим интеллектуальным указателем, необработанным указателем на интерфейс или **NULL**.|  
|[Средства извлечения](../cpp/com-ptr-t-extractors.md)|Извлекают инкапсулированный указатель на COM-интерфейс.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** comip.h  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)
