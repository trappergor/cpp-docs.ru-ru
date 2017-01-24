---
title: "Класс _com_ptr_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t - класс"
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс _com_ptr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Объект `_com_ptr_t` инкапсулирует указатель на COM\-интерфейс и называется интеллектуальным указателем.  Этот класс шаблона управляет выделением и освобождением ресурсов с помощью вызовов следующих функций\-членов **IUnknown**: `QueryInterface`, `AddRef` и **Release**.  
  
 Ссылка на интеллектуальный указатель обычно осуществляется с помощью определения typedef, предоставляемого макросом **\_COM\_SMARTPTR\_TYPEDEF**.  Этот макрос имеет имя интерфейса и IID и объявляет специализацию объекта `_com_ptr_t`, используя имя интерфейса и суффикс `Ptr`.  Например:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 объявляет специализацию **IMyInterfacePtr** объекта `_com_ptr_t`.  
  
 Набор [шаблонов функций](../cpp/relational-function-templates.md) \(не являющихся членами этого класса шаблона\) поддерживает сравнение с интеллектуальным указателем в правой части оператора сравнения.  
  
### Создание  
  
|||  
|-|-|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-com-ptr-t.md)|Создает объект `_com_ptr_t`.|  
  
### Низкоуровневые операции  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Вызывает функцию\-член `AddRef` **IUnknown** в инкапсулированном указателе на интерфейс.|  
|[Attach](../Topic/_com_ptr_t::Attach.md)|Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Создает новый экземпляр объекта, учитывая **CLSID** или **ProgID**.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Извлекает и возвращает инкапсулированный указатель на интерфейс.|  
|[GetActiveObject](../Topic/_com_ptr_t::GetActiveObject.md)|Добавляет к существующему экземпляру объекта, заданного значением **CLSID** или **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Возвращает инкапсулированный указатель на интерфейс.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Вызывает функцию\-член `QueryInterface` **IUnknown** в инкапсулированном указателе на интерфейс.|  
|[Release](../cpp/com-ptr-t-release.md)|Вызывает функцию\-член **Release IUnknown** в инкапсулированном указателе на интерфейс.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../cpp/com-ptr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_com_ptr_t`.|  
|[operators \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/com-ptr-t-relational-operators.md)|Сравнивают объект интеллектуального указателя с другим интеллектуальным указателем, необработанным указателем на интерфейс или значением **NULL**.|  
|[Средства извлечения](../cpp/com-ptr-t-extractors.md)|Извлекают инкапсулированный указатель на COM\-интерфейс.|  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 **Заголовок:** comip.h  
  
 **Библиотека:** comsuppw.lib или comsuppwd.lib \(дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)\)  
  
## См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)