---
title: "Класс codecvt_byname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt_byname
- xlocale/std::codecvt_byname
dev_langs:
- C++
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 39128e8aa23e40489a02d5f2abf834c8f003a41d
ms.lasthandoff: 02/24/2017

---
# <a name="codecvtbyname-class"></a>Класс codecvt_byname
Производный класс шаблона, описывающий объект, который можно использовать как аспект сортировки данного языкового стандарта, предоставляющий возможность извлечения данных касательно преобразований по соответствующему культурному региону.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
```
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```  
  
```
protected:
    virtual ~codecvt_byname();

};
```  
  
#### <a name="parameters"></a>Параметры  
 `_Locname`  
 Именованный языковой стандарт.  
  
 `_Refs`  
 Начальное значение счетчика ссылок.  
  
## <a name="remarks"></a>Примечания  
 Аспекты Byname создаются автоматически при создании именованного языкового стандарта.  
  
 Его поведение определяется именованным языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




