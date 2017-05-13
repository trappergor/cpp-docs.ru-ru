---
title: "Класс codecvt_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt_base
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
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
ms.openlocfilehash: d0c12f0dfb1b0ceb111f3c3313e78dd5c9197f70
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="codecvtbase-class"></a>Класс codecvt_base
Базовый класс для класса codecvt, используемый для определения типа перечисления с именем **result**, который применяется в качестве типа возвращаемого значения для функций-членов аспекта, чтобы показать результат преобразования.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```  
  
## <a name="remarks"></a>Примечания  
 Данный класс описывает перечисление, общее для всех специализаций класса-шаблона [codecvt](../standard-library/codecvt-class.md). Результат перечисления описывает возможные возвращаемые значения из [do_in](../standard-library/codecvt-class.md#do_in) или [do_out](../standard-library/codecvt-class.md#do_out):  
  
- **ОК**, если преобразование между внутренней и внешней кодировками символов выполняется успешно.  
  
- **partial**, если целевой объект недостаточно велик для успешного преобразования.  
  
- **error**, если исходная последовательность имеет неправильную форму.  
  
- **noconv**, если функция не выполняет преобразование.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




