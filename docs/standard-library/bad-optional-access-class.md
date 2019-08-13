---
title: Класс bad_optional_access
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: 043b0360c7e0be48267c8f406dbfea50eeb5a8e3
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957102"
---
# <a name="bad_optional_access-class"></a>Класс bad_optional_access

Определяет тип объектов, создаваемых как исключения, для сообщения о ситуации, когда предпринимается попытка доступа к значению `optional` объекта, который не содержит значения.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>См. также

[\<Необязательный >](optional.md)\
[необязательный класс](optional-class.md)
