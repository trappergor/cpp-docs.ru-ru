---
title: "Understanding Parse Trees | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parse trees"
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Understanding Parse Trees
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно указать один или несколько анализе деревья в скрипте регистратора, где каждый дерево синтаксического анализа имеет следующую форму:  
  
```  
<root key>{<registry expression>}+  
```  
  
 Здесь:  
  
```  
<root key> ::=  HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
               HKEY_LOCAL_MACHINE | HKEY_USERS |  
               HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
               HKEY_CURRENT_CONFIG | HKCR | HKCU |  
               HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
              [<Key Value>][{< Add Key>}]  
<Delete Key> ::=  Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
>  `HKEY_CLASSES_ROOT` и `HKCR` эквивалентны. `HKEY_CURRENT_USER` и `HKCU` эквивалентны. и т д  
  
 Дерево синтаксического разбора может добавлять несколько ключей и подразделы в \<root key\>.  В этом он содержит открытый маркера подраздела до тех пор, пока средство синтаксического анализа не завершится проанализировать все его подразделов.  Этот подход является более эффективным, чем работе над одним ключом, как показано в следующем примере.  
  
```  
HKEY_CLASSES_ROOT  
{  
   'MyVeryOwnKey'  
   {  
      'HasASubKey'  
      {  
         'PrettyCool?'  
      }  
   }  
}  
```  
  
 Здесь регистратор исходной открывает \(создает\) `HKEY_CLASSES_ROOT\MyVeryOwnKey`.  Затем он см. в разделе что `MyVeryOwnKey` имеет подраздела.  Вместо того, чтобы закрыть ключ к `MyVeryOwnKey`, регистратор сохраняет дескриптор \(создание и открытие\) `HasASubKey` используя этот родительский дескриптор.  \(Реестру системы может быть медленнее, если родительский дескриптор не открыт\). Таким образом, открыв `HKEY_CLASSES_ROOT\MyVeryOwnKey` а затем при открытии `HasASubKey` с `MyVeryOwnKey`, что и родительский быстрее, чем при открытии `MyVeryOwnKey`, заключительное `MyVeryOwnKey`, а затем при открытии `MyVeryOwnKey\HasASubKey`.  
  
## См. также  
 [Creating Registrar Scripts](../Topic/Creating%20Registrar%20Scripts.md)