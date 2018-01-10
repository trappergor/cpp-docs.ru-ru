---
title: "Класс ctype_byname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocale/std::ctype_byname
dev_langs: C++
helpviewer_keywords: ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 552e482933def86bfd9812a725ddc4553f4f8ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctypebyname-class"></a>Класс ctype_byname
Производный класс шаблона, описывающий объект, который можно использовать в качестве аспекта ctype заданного языкового стандарта, позволяющий классифицировать символы и выполнять преобразование символов в другой регистр, а также из внутреннего набора символов в набор символов, заданный для языкового стандарта, и наоборот.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```  
  
## <a name="remarks"></a>Примечания  
 Его поведение определяется именованным языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) или эквивалент для базового класса `ctype<char>`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



