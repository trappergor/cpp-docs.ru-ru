---
title: Примеры сценариев реестра
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 7bcdb7076982e2f0bd08f4fd82bb45f21e61ef20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329326"
---
# <a name="registry-scripting-examples"></a>Примеры сценариев реестра

Примеры сценариев в этой теме демонстрируют, как добавить ключ к реестру системы, зарегистрировать сервер Регистратора COM и указать несколько деревьев разбора.

## <a name="add-a-key-to-hkey_current_user"></a>Добавить ключ к HKEY_CURRENT_USER

Следующее дерево разбора иллюстрирует простой скрипт, который добавляет один ключ к реестру системы. В частности, скрипт `MyVeryOwnKey`добавляет `HKEY_CURRENT_USER`ключ, чтобы . Он также присваивает `HowGoesIt` значение строки по умолчанию новому ключу:

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Этот скрипт можно легко расширить, чтобы определить несколько подключ следующим образом:

```
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

Теперь, скрипт добавляет `HasASubkey`подключку, , чтобы `MyVeryOwnKey`. К этому подключке `PrettyCool` он добавляет как `DWORD` подключьку (со `ANameValue` значением по умолчанию `WithANamedValue`55), так и названное значение (со значением строки).

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>Регистрация регистратора COM Server

Следующий скрипт регистрирует сам сервер Регистраторcom COM.

```
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

Во время выполнения, это дерево `ATL.Registrar` разбора `HKEY_CLASSES_ROOT`добавляет ключ к . К этому новому ключу, оно после этого:

- `ATL Registrar Class` Определяется как значение строки по умолчанию ключа.

- Добавляет `CLSID` в качестве подключаемого ключа.

- Указывает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` на `CLSID`. (Это значение CLSID Регистратора для использования с `CoCreateInstance`.)

Поскольку `CLSID` он является общим, он не должен быть удален в режиме unregister. Заявление, `NoRemove CLSID`делает это, указывая, что `CLSID` должны быть открыты в режиме регистра и игнорируются в режиме unregister.

Заявление `ForceRemove` обеспечивает функцию домашнего хозяйства, удалив ключ и все его подки перед воссозданием ключа. Это может быть полезно, если имена подключки изменились. В этом примере `ForceRemove` скриптов `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` проверяйте, существует ли уже. Если это `ForceRemove`так, :

- Рекурсивно удаляет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` и все его подки.

- Воссоздает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- Добавляет `ATL Registrar Class` в качестве значения `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`строки по умолчанию для .

Дерево разбора теперь добавляет два `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`новых подключки к . Первый ключ, `ProgID`получает значение строки по умолчанию, то есть ProgID. Второй ключ, `InprocServer32`, получает значение `%MODULE%`строки по умолчанию, то есть значение предварительного процессора, объясняемого в разделе, [Используя заменяемые параметры (Препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), этой статьи. `InprocServer32`также получает названное значение, `ThreadingModel`, `Apartment`с значением шнура .

## <a name="specify-multiple-parse-trees"></a>Укажите несколько парсовых деревьев

Чтобы указать более одного дерева разбора в скрипте, просто поместите одно дерево в конце другого. Например, следующий скрипт `MyVeryOwnKey`добавляет ключ, к разбору `HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER`деревьев для обоих и:

```
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> В скрипте регистратора 4K является максимальным размером маркера. (Токен – это любой узнаваемый элемент в синтаксисе.) В предыдущем примере `HKCR`сценариев, , `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`и `'HowGoesIt'` все жетоны.

## <a name="see-also"></a>См. также раздел

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
