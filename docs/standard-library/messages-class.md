---
title: "Класс messages | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- messages
- xlocmes/std::messages
- locale/std::messages::char_type
- locale/std::messages::string_type
- locale/std::messages::close
- locale/std::messages::do_close
- locale/std::messages::do_get
- locale/std::messages::do_open
- locale/std::messages::get
- locale/std::messages::open
dev_langs:
- C++
helpviewer_keywords:
- messages class
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8a3c647c9c64f2783bf2bc6d2eee86d7107af8d2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="messages-class"></a>Класс messages
Класс шаблона, описывающий объект, который можно использовать в качестве аспекта языкового стандарта для извлечения локализованных сообщений из каталога интернационализированных сообщений для заданного языкового стандарта.  
  
 В настоящее время при использовании данного класса сообщений сообщения не создаются.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class CharType>  
class messages : public messages_base;
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**  
  
 По сути, этот аспект открывает каталог сообщений, заданных в базовом классе messages_base, извлекает необходимую информацию и закрывает каталог.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[messages](#messages)|Функция конструктора аспекта сообщения.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|Тип символа, используемого для отображения сообщений.|  
|[string_type](#string_type)|Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[close](#close)|Закрывает каталог сообщений.|  
|[do_close](#do_close)|Виртуальная функция, вызываемая для закрытия каталога сообщений.|  
|[do_get](#do_get)|Виртуальная функция, вызываемая для извлечения каталога сообщений.|  
|[do_open](#do_open)|Виртуальная функция, вызываемая для открытия каталога сообщений.|  
|[get](#get)|Извлекает каталог сообщений.|  
|[open](#open)|Открывает каталог сообщений.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
##  <a name="char_type"></a>  messages::char_type  
 Тип символа, используемого для отображения сообщений.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для параметра-шаблона **Chartype**.  
  
##  <a name="close"></a>  messages::close  
 Закрывает каталог сообщений.  
  
```
void close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catval`  
 Каталог для закрытия.  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает [do_close](#do_close)(_ *Catval*).  
  
##  <a name="do_close"></a>  messages::do_close  
 Виртуальная функция, вызываемая для закрытия каталога сообщений.  
  
```
virtual void do_close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catval`  
 Каталог для закрытия.  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член закрывает каталог сообщений `_Catval`, который должен быть открыт предшествующим вызовом [do_open](#do_open).  
  
 Значение *_Catval* должно быть получено из ранее открытого каталога, который не закрыт.  
  
### <a name="example"></a>Пример  
  См. пример для [close](#close), в котором вызывается `do_close`.  
  
##  <a name="do_get"></a>  messages::do_get  
 Виртуальная функция, вызываемая для извлечения каталога сообщений.  
  
```
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catval`  
 Значение идентификации, указывающее каталог сообщений для поиска.  
  
 `_Set`  
 Первый идентификатор, использованный для поиска сообщения в каталоге сообщений.  
  
 `_Message`  
 Второй идентификатор, использованный для поиска сообщения в каталоге сообщений.  
  
 `_Dfault`  
 Строка, которая будет возвращаться при сбое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию `_Dfault` в случае сбоя. В противном случае он возвращает копию указанной последовательности сообщений.  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член пытается получить последовательность сообщений из каталога сообщений `_Catval`. Она может при этом использовать `_Set`, `_Message` и `_Dfault`.  
  
### <a name="example"></a>Пример  
  См. пример для [get](#get), в котором вызывается `do_get`.  
  
##  <a name="do_open"></a>  messages::do_open  
 Виртуальная функция, вызываемая для открытия каталога сообщений.  
  
```
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catname`  
 Имя каталога для поиска.  
  
 `_Loc`  
 Языковой стандарт, который ищется в каталоге.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Он возвращает значение, которое при сбое получает значение меньше нуля. В противном случае возвращаемое значение может использоваться в качестве первого аргумента в последующем вызове [get](#get).  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член пытается открыть каталог сообщений с именем `_Catname`. Она может при этом использовать языковой стандарт `_Loc`  
  
 Возвращаемое значение следует использовать как аргумент для последующего вызова [close](#close).  
  
### <a name="example"></a>Пример  
  См. пример для [open](#open), в котором вызывается `do_open`.  
  
##  <a name="get"></a>  messages::get  
 Извлекает каталог сообщений.  
  
```
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catval`  
 Значение идентификации, указывающее каталог сообщений для поиска.  
  
 `_Set`  
 Первый идентификатор, использованный для поиска сообщения в каталоге сообщений.  
  
 `_Message`  
 Второй идентификатор, использованный для поиска сообщения в каталоге сообщений.  
  
 `_Dfault`  
 Строка, которая будет возвращаться при сбое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию `_Dfault` в случае сбоя. В противном случае он возвращает копию указанной последовательности сообщений.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_get](#do_get)(`_Catval`, `_Set`, `_Message`, `_Dfault`).  
  
##  <a name="messages"></a>  messages::messages  
 Функция конструктора аспекта сообщения.  
  
```
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение, используемое для указания типа управления памятью для объекта.  
  
 `_Locname`  
 Имя языкового стандарта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` и их важность:  
  
-   0: время существования объекта управляется языковыми стандартами, которые его содержат.  
  
-   1: время существования объекта должно управляться вручную.  
  
-   \>1: эти значения не определены.  
  
 Прямые примеры привести нельзя, так как деструктор защищен.  
  
 Конструктор инициализирует свой базовый объект с **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="open"></a>  messages::open  
 Открывает каталог сообщений.  
  
```
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Catname`  
 Имя каталога для поиска.  
  
 `_Loc`  
 Языковой стандарт, который ищется в каталоге.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Он возвращает значение, которое при сбое получает значение меньше нуля. В противном случае возвращаемое значение может использоваться в качестве первого аргумента в последующем вызове [get](#get).  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_open](#do_open)(`_Catname`, `_Loc`).  
  
##  <a name="string_type"></a>  messages::string_type  
 Тип, описывающий строку типа `basic_string`, содержащую символы типа **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [basic_string](../standard-library/basic-string-class.md), объекты которого могут хранить копии последовательностей сообщений.  
  
## <a name="see-also"></a>См. также  
 [\<locale>](../standard-library/locale.md)   
 [Класс messages_base](../standard-library/messages-base-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




