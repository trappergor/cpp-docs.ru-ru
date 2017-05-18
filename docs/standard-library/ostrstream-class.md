---
title: "Класс ostrstream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostrstream
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- ostrstream class
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
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
ms.openlocfilehash: 2ed85552778f3bbf7346001e4dd4c858177ce49b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ostrstream-class"></a>Класс ostrstream
Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ostrstream : public ostream
```  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет объект класса `strstreambuf`.  
  
> [!NOTE]
>  Этот класс устарел. Вместо него рекомендуется использовать [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) или [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[ostrstream](#ostrstream)|Создает объект типа `ostrstream`.|  
  
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
  
##  <a name="freeze"></a>  ostrstream::freeze  
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
  См. раздел [strstream::freeze](../standard-library/strstreambuf-class.md#freeze) с примером использования **freeze**.  
  
##  <a name="ostrstream"></a>  ostrstream::ostrstream  
 Создает объект типа `ostrstream`.  
  
```
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Буфер.  
  
 `count`  
 Размер буфера в байтах.  
  
 `_Mode`  
 Режим ввода-вывода буфера. См. раздел [ios_base::openmode](../standard-library/ios-base-class.md#openmode) для получения дополнительной информации.  
  
### <a name="remarks"></a>Примечания  
 Оба конструктора инициализируют базовый класс путем вызова [ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**), где **sb** является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализирует **sb** путем вызова `strstreambuf`. Второй конструктор инициализирует базовый класс одним из двух способов:  
  
-   Если `_Mode`  &  **ios_base::app**== 0, то `ptr` должен назначить первый элемент массива из `count` элементов. Далее конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`).  
  
-   В противном случае `ptr` должен назначить первый элемент массива элементов-счетчиков, содержащий строку C, первый элемент которой обозначается `ptr`. Затем конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`  +  `strlen`(`ptr`)).  
  
##  <a name="pcount"></a>  ostrstream::pcount  
 Возвращает число элементов, записанных в управляемую последовательность.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, записанных в управляемую последовательность.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).  
  
### <a name="example"></a>Пример  
  См. раздел [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `pcount`.  
  
##  <a name="rdbuf"></a>  ostrstream::rdbuf  
 Возвращает указатель на объект strstreambuf, связанный с потоком.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект strstreambuf, связанный с потоком.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает адрес хранимого буфера потока типа **pointer**, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Пример  
  См. раздел [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `rdbuf`.  
  
##  <a name="str"></a>  ostrstream::str  
 Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на начало управляемой последовательности.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Пример  
  См. раздел [strstream::str](../standard-library/strstreambuf-class.md#str) с примером использования **str**.  
  
## <a name="see-also"></a>См. также  
 [ostream](../standard-library/ostream-typedefs.md#ostream)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)




