---
title: Регистратор ATL и деревья синтаксического анализа
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: ff74ff879e757a569232ff19244d3f7598063465
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040292"
---
# <a name="understanding-parse-trees"></a>Основные сведения о деревьях синтаксического анализа

В скрипте регистратора можно определить одно или несколько деревьев синтаксического анализа, где каждое дерево синтаксического анализа имеет следующую форму:

> \<root key>{\<registry expression>}+

где:

> \<root key> :: = HKEY_CLASSES_ROOT \| HKEY_CURRENT_USER \|\
> &emsp;HKEY_LOCAL_MACHINE \| HKEY_USERS \|\
> &emsp;HKEY_PERFORMANCE_DATA \| HKEY_DYN_DATA \|\
> &emsp;HKEY_CURRENT_CONFIG \| HKCR \| HKCU \|\
> &emsp;HKLM \| HKU \| хкпд \| хкдд \| хккк

> \<registry expression>::= \<Add Key> \|\<Delete Key>

> \<Add Key>:: = \[ **ForceRemove** \| **Удалить** \| **Val**] \<Key Name> [ \<Key Value> ] [{ \<Add Key> }]

> \<Delete Key> :: = **Delete**\<Key Name>

> \<Key Name> ::= **'**\<AlphaNumeric>+**'**

> \<AlphaNumeric> :: = *любой символ, не равный null, т. е. ASCII 0*

> \<Key Value> ::= \<Key Type>\<Key Name>

> \<Key Type> :: = **s** \| **d**

> \<Key Value> ::= **'**\<AlphaNumeric>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT` и `HKCR` являются эквивалентными; `HKEY_CURRENT_USER` и `HKCU` эквивалентны; и т. д.

Дерево синтаксического анализа может добавлять в. несколько ключей и подразделов \<root key> . В этом случае обработчик подраздела остается открытым до тех пор, пока синтаксический анализатор не завершит анализ всех подразделов. Этот подход более эффективен, чем работа с одним ключом за раз, как показано в следующем примере:

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

Здесь сначала открывается регистратор (создает) `HKEY_CLASSES_ROOT\MyVeryOwnKey` . Затем он видит, что `MyVeryOwnKey` имеет подраздел. Вместо того, чтобы закрывать ключ `MyVeryOwnKey` , регистратор удерживает этот обработчик и открывает (создает) его `HasASubKey` с помощью этого родительского маркера. (Если родительский обработчик не открыт, системный реестр может быть медленнее.) Таким образом, открытие `HKEY_CLASSES_ROOT\MyVeryOwnKey` , а затем открытие `HasASubKey` с помощью в `MyVeryOwnKey` качестве родителя выполняется быстрее, чем открытие `MyVeryOwnKey` , закрытие `MyVeryOwnKey` , а затем открытие `MyVeryOwnKey\HasASubKey` .

## <a name="see-also"></a>См. также раздел

[Создание скриптов регистратора](../atl/creating-registrar-scripts.md)
