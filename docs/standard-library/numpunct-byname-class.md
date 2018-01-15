---
title: "Класс numpunct_byname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocnum/std::numpunct_byname
dev_langs: C++
helpviewer_keywords: numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84f71302d43a983772890611e55c56af9b21e922
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="numpunctbyname-class"></a>Класс numpunct_byname
Производный класс шаблона, описывающий объект, который можно использовать в качестве аспекта `numpunct` для заданного языкового стандарта, для возможности форматирования и расстановки пунктуационных знаков в числовых и логических выражениях.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

 };
```  
  
## <a name="remarks"></a>Примечания  
 Его поведение определяется [именованным](../standard-library/locale-class.md#name) языковым стандартом `_Locname`. Конструктор инициализирует свой базовый объект с [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>( `_Refs`).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



