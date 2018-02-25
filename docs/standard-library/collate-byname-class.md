---
title: "Класс collate_byname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2682abebd6528edbdbec1f6fb1a00082436f1299
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
 Класс шаблона, описывающий объект, который может служить в качестве [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class) типа [collate](../standard-library/collate-class.md#collate)\<CharType>. Его поведение определяется [именованным](../standard-library/locale-class.md#name) языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



