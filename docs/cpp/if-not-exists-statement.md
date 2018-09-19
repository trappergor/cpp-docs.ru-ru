---
title: оператор __if_not_exists | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66999d99e7809a3588dc3c92cae822bb4295ee07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073360"
---
# <a name="ifnotexists-statement"></a>Оператор __if_not_exists

**__If_not_exists** инструкции проверяет, является ли указанный идентификатор существует. Если идентификатор не существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_not_exists ( identifier ) { 
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*identifier*|Идентификатор, наличие которого требуется проверить.|
|*Инструкции*|Один или несколько операторов для выполнения, если *идентификатор* не существует.|

## <a name="remarks"></a>Примечания

> [!CAUTION]
>  Для достижения самых надежных результатов используйте **__if_not_exists** инструкции с учетом следующих ограничений.

- Применить **__if_not_exists** инструкцию, чтобы только простые типы, не шаблоны.

- Применить **__if_not_exists** инструкции к идентификаторам как внутри, так и вне класса. Не устанавливайте **__if_not_exists** инструкции для локальных переменных.

- Используйте **__if_not_exists** инструкции только в теле функции. За пределами тела функции **__if_not_exists** инструкция может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнением к **__if_not_exists** инструкция является [__if_exists](../cpp/if-exists-statement.md) инструкции.

## <a name="example"></a>Пример

Пример использования **__if_not_exists**, см. в разделе [__if_exists инструкции](../cpp/if-exists-statement.md).

## <a name="see-also"></a>См. также

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор __if_exists](../cpp/if-exists-statement.md)