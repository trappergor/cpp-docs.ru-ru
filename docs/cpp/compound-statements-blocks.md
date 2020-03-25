---
title: Составные операторы (блоки)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: cd0e5daa2232f17a34bee2f0d8b9569e524fbf34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189563"
---
# <a name="compound-statements-blocks"></a>Составные операторы (блоки)

Составной оператор состоит из нуля или более операторов, заключенных в фигурные скобки ( **{}** ). Составной оператор может использоваться везде, где ожидается оператор. Составные инструкции часто называются "блоками".

## <a name="syntax"></a>Синтаксис

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Remarks

В следующем примере составной оператор используется *как часть оператора* if оператора **If** (Дополнительные сведения о синтаксисе см. [в инструкции If](../cpp/if-else-statement-cpp.md) ).

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
>  Поскольку объявление является оператором, объявление может быть одной из инструкций в *списке инструкций*. Таким образом, имена, которые были объявлены в составном операторе, но не были явно объявлены как статичные, имеют локальную область видимости, а объекты — еще и локальное время существования. Дополнительные сведения об обработке имен с локальной областью см. в разделе [область](../cpp/scope-visual-cpp.md) .

## <a name="see-also"></a>См. также раздел

[Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)
