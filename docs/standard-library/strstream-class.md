---
title: "Класс strstream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strstream
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
dev_langs:
- C++
helpviewer_keywords:
- strstream class
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a1d7d7799e1338c72404f5bcdb9d06e9bac763e5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="strstream-class"></a>Класс strstream
Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class strstream : public iostream
```  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет объект класса `strstreambuf`.  
  
> [!NOTE]
>  Этот класс устарел. Вместо него рекомендуется использовать [stringstream](../standard-library/sstream-typedefs.md#stringstream) или [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[strstream](#strstream)|Создает объект типа `strstream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[freeze](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|  
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|  
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|  
|[str](#str)|Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<strstream>  
  
 **Пространство имен:** std  
  
##  <a name="freeze"></a>  strstream::freeze  
 Делает буфер потока недоступным для операций с буфером потока.  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>Параметры  
 `_Freezeit`  
 Объект `bool`, указывающий, следует ли фиксировать поток.  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает метод [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).  
  
### <a name="example"></a>Пример  
  См. пример использования метода **freeze** в разделе [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze)  
  
##  <a name="pcount"></a>  strstream::pcount  
 Возвращает число элементов, записанных в управляемую последовательность.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, записанных в управляемую последовательность.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).  
  
### <a name="example"></a>Пример  
  См. пример использования метода pcount в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="rdbuf"></a>  strstream::rdbuf  
 Возвращает указатель на объект strstreambuf, связанный с потоком.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект strstreambuf, связанный с потоком.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает адрес хранимого буфера потока типа **pointer**, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Пример  
  См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="str"></a>  strstream::str  
 Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на начало управляемой последовательности.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Пример  
  См. пример использования **str** в разделе [strstreambuf::str](../standard-library/strstreambuf-class.md#str).  
  
##  <a name="strstream"></a>  strstream::strstream  
 Создает объект типа `strstream`.  
  
```
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Размер буфера.  
  
 `_Mode`  
 Режим ввода-вывода буфера. Дополнительные сведения см. в разделе [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `ptr`  
 Буфер.  
  
### <a name="remarks"></a>Примечания  
 Оба конструктора инициализируют базовый класс путем вызова [streambuf](../standard-library/streambuf-typedefs.md#streambuf)(**sb**), где **sb** является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализирует **sb**, вызывая метод [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Второй конструктор инициализирует базовый класс одним из двух способов:  
  
-   Если `_Mode`  &  **ios_base::app**== 0, то `ptr` должен назначить первый элемент массива из `count` элементов. Далее конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`).  
  
-   В противном случае `ptr` должен назначить первый элемент массива элементов-счетчиков, содержащий строку C, первый элемент которой обозначается `ptr`. Затем конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`  +  `strlen`(`ptr`)).  
  
## <a name="see-also"></a>См. также  
 [iostream](../standard-library/istream-typedefs.md#iostream)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)




