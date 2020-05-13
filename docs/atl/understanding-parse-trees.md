---
title: Регистратор ATL и деревья синтаксического анализа
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: de2cea9b0e7b7c62236f708f9aa8217eaa5df51d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168700"
---
# <a name="understanding-parse-trees"></a>Основные сведения о деревьях синтаксического анализа

В скрипте регистратора можно определить одно или несколько деревьев синтаксического анализа, где каждое дерево синтаксического анализа имеет следующую форму:

> \<корневой ключ>\<{выражение реестра>} +

Где:

> \<корневой ключ>:: = HKEY_CLASSES_ROOT | HKEY_CURRENT_USER | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_LOCAL_MACHINE | HKEY_USERS | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_CURRENT_CONFIG | HKCR | HKCU | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKLM | HKU | ХКПД | ХКДД | хккк

> \<выражение реестра>:: = \<добавить ключ> | \<Удалить ключ>

> \<Добавьте ключевое>:: = [**ForceRemove** | **Удаление** | **Val**]\<имя ключа> [\<значение ключа>] [{\<добавить ключ>}]

> \<Удалите ключ>:: = **Delete**\<имя ключа>

> \<Имя ключа>:: = **"**\<буквенно-цифровой>+**"**

> \<Буквенно-цифровые>:: = *любой символ, не равный null, т. е. ASCII 0*

> \<Значение ключа>:: = \<тип ключа>\<имя ключа>

> \<Тип ключа>:: = **s** | **d**

> \<Значение ключа>:: = **"**\<буквенно-цифровой>**"**

> [!NOTE]
> `HKEY_CLASSES_ROOT`и `HKCR` являются эквивалентными; `HKEY_CURRENT_USER` и `HKCU` являются эквивалентными; и т. д.

Дерево синтаксического анализа может добавлять к \<корневому ключу несколько ключей и подразделов>. В этом случае обработчик подраздела остается открытым до тех пор, пока синтаксический анализатор не завершит анализ всех подразделов. Этот подход более эффективен, чем работа с одним ключом за раз, как показано в следующем примере:

```rgs
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

Здесь сначала открывается регистратор (создает) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Затем он видит, `MyVeryOwnKey` что имеет подраздел. Вместо того, чтобы `MyVeryOwnKey`закрывать ключ, регистратор удерживает этот обработчик и открывает (создает) `HasASubKey` его с помощью этого родительского маркера. (Если родительский обработчик не открыт, системный реестр может быть медленнее.) Таким образом, `HKEY_CLASSES_ROOT\MyVeryOwnKey` открытие, а `HasASubKey` затем `MyVeryOwnKey` открытие с помощью в качестве родителя выполняется `MyVeryOwnKey`быстрее, `MyVeryOwnKey`чем открытие, закрытие `MyVeryOwnKey\HasASubKey`, а затем открытие.

## <a name="see-also"></a>См. также

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
