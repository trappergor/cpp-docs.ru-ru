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
ms.openlocfilehash: 60d7e88c5ccccac5a1d967a91c8a82dd954d9afc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337342"
---
# <a name="compound-statements-blocks"></a>Составные операторы (блоки)

Соединение оператора состоит из нуля или более заявлений, заключенных в фигурные скобки **(** Составной оператор может использоваться везде, где ожидается оператор. Составные инструкции часто называются "блоками".

## <a name="syntax"></a>Синтаксис

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Remarks

В следующем примере соединение оператора используется *в* качестве части оператора **if** (см. сведения о синтаксисе if [Statement):](../cpp/if-else-statement-cpp.md)

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
> Поскольку декларация является заявлением, декларация может быть одним из заявлений в *списке заявлений.* Таким образом, имена, которые были объявлены в составном операторе, но не были явно объявлены как статичные, имеют локальную область видимости, а объекты — еще и локальное время существования. См [См. Область](../cpp/scope-visual-cpp.md) для получения подробной информации об обращении с именами с локальной областью.

## <a name="see-also"></a>См. также раздел

[Обзор заявлений по СЗ](../cpp/overview-of-cpp-statements.md)
