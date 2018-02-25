---
title: "Класс istrstream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aec0c2bbac29da5406002aefbd6a6adcac926a33
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="istrstream-class"></a>Класс istrstream
Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет объект класса `strstreambuf`.  
  
> [!NOTE]
>  Этот класс устарел. Вместо него рекомендуется использовать [istringstream](../standard-library/sstream-typedefs.md#istringstream) или [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[istrstream](#istrstream)|Создает объект типа `istrstream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|  
|[str](#str)|Вызывает метод [freeze](../standard-library/strstreambuf-class.md#freeze), а затем возвращает указатель на начало управляемой последовательности.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<strstream>  
  
 **Пространство имен:** std  
  
##  <a name="istrstream"></a>  istrstream::istrstream  
 Создает объект типа `istrstream`.  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Длина буфера ( `ptr`).  
  
 `ptr`  
 Содержимое, с которым инициализируется буфер.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы инициализируют базовый класс путем вызова [istream](../standard-library/istream-typedefs.md#istream)( **sb**), где **sb** является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первые два конструктора также инициализируют **sb** путем вызова `strstreambuf`( ( **const**`char` \*) `ptr`, 0 ). Оставшиеся два конструктора вместо этого вызывают `strstreambuf`( ( **const**`char` *) `ptr`, `count` ).  
  
##  <a name="rdbuf"></a>  istrstream::rdbuf  
 Возвращает указатель на объект strstreambuf, связанный с потоком.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект strstreambuf, связанный с потоком.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает адрес хранимого буфера потока типа pointer, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Пример  
  См. раздел [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `rdbuf`.  
  
##  <a name="str"></a>  istrstream::str  
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
 [istream](../standard-library/istream-typedefs.md#istream)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



