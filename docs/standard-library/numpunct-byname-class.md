---
title: Класс numpunct_byname
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: 64e8918b052b05088ff48aefb0f0f9ab8c6df586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432877"
---
# <a name="numpunctbyname-class"></a>Класс numpunct_byname

Производный класс шаблона, описывающий объект, который можно использовать в качестве аспекта `numpunct` для заданного языкового стандарта, для возможности форматирования и расстановки пунктуационных знаков в числовых и логических выражениях.

## <a name="syntax"></a>Синтаксис

```cpp
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

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
