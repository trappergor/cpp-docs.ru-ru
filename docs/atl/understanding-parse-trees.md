---
title: "Регистратор ATL и синтаксический анализ деревьев | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8ce648a541f6e0e2d4fac2e6ee19226e41f20ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-parse-trees"></a>Основные сведения о деревьях синтаксического анализа
Можно определить одно или несколько деревьев синтаксический анализ скрипта регистратора, где каждое дерево синтаксического анализа имеет следующий вид:  
  
```  
<root key>{<registry expression>}+  
```  
  
 Здесь:  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT`и `HKCR` эквивалентны; `HKEY_CURRENT_USER` и `HKCU` эквивалентны; т. д.  
  
 Дерево синтаксического анализа можно добавить несколько разделов и подразделов в \<корневого ключа >. При этом он поддерживает дескриптор соответствующий раздел реестра открытым до завершения синтаксического анализа, все его подразделы средство синтаксического анализа. Такой подход более эффективен, чем работы с одним ключом одновременно, как показано в следующем примере:  
  
```  
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
  
 Здесь, изначально открывает регистратора (создает) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Затем видит, что `MyVeryOwnKey` имеется подраздел. Вместо того, чтобы закрыть ключ `MyVeryOwnKey`, регистратор сохраняет дескриптор и открывает (создает) `HasASubKey` с помощью данного дескриптора родительского. (Системного реестра может быть медленнее, если открыт дескриптор родительского.) Таким образом, открыв `HKEY_CLASSES_ROOT\MyVeryOwnKey` и откройте `HasASubKey` с `MyVeryOwnKey` как родительский выполняется быстрее, чем Открытие `MyVeryOwnKey`, закрытие `MyVeryOwnKey`и откройте `MyVeryOwnKey\HasASubKey`.  
  
## <a name="see-also"></a>См. также  
 [Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

