---
title: Оператор __if_not_exists
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 1118f9fcca525b2b2d5869fb507ee974d2b0d28f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374139"
---
# <a name="__if_not_exists-statement"></a>Оператор __if_not_exists

В **__if_not_exists** выписке проверяется, существует ли указанный идентификатор. Если идентификатор не существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Идентификатор*|Идентификатор, наличие которого требуется проверить.|
|*Заявления*|Одно или несколько утверждений для выполнения, если *идентификатор* не существует.|

## <a name="remarks"></a>Remarks

> [!CAUTION]
> Для достижения наиболее надежных результатов используйте **__if_not_exists** заявление под следующими ограничениями.

- Примените **__if_not_exists** заявление только к простым типам, а не к шаблонам.

- Примените **__if_not_exists** заявление к идентификаторам как внутри, так и за пределами класса. Не **применяйте** __if_not_exists заявление к локальным переменным.

- Используйте **__if_not_exists** оператора только в теле функции. Вне тела функции, **__if_not_exists** оператора может тестировать только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнением к **заявлению __if_not_exists** является [заявление __if_exists.](../cpp/if-exists-statement.md)

## <a name="example"></a>Пример

Например, как использовать **__if_not_exists,** с [__if_existsм.](../cpp/if-exists-statement.md)

## <a name="see-also"></a>См. также раздел

[Инструкции выбора](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[Заявление __if_exists](../cpp/if-exists-statement.md)
