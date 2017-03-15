---
title: "Класс collate_byname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::collate_byname
- locale/std::collate_byname
- std.collate_byname
- collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
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
ms.openlocfilehash: a67e7f6ff915b53ba91c11c0c39d9bec6e4a380a
ms.lasthandoff: 02/24/2017

---
# <a name="collatebyname-class"></a>Класс collate_byname
Производный класс шаблона, описывающий объект, который можно использовать как аспект сортировки данного языкового стандарта, предоставляющий возможность извлечения данных касательно сортировки строк по соответствующему культурному региону.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>Параметры  
 `_Locname`  
 Именованный языковой стандарт.  
  
 `_Refs`  
 Начальное значение счетчика ссылок.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона, описывающий объект, который может служить в качестве [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class) типа [collate](../standard-library/collate-class.md#collate__collate)\<CharType>. Его поведение определяется [именованным](../standard-library/locale-class.md#locale__name) языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [collate](../standard-library/collate-class.md#collate__collate)\<CharType>( `_Refs`).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




