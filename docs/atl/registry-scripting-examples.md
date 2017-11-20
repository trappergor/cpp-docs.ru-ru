---
title: "Примеры сценариев реестра | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcb1b2307ccb16e7b842e221c48c0f2a99b31db6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="registry-scripting-examples"></a>Примеры сценариев реестра
Примеры сценариев в этом разделе показано, как добавить раздел в системный реестр, Регистрация сервера регистрации COM и указать несколько синтаксический анализ деревьев.  
  
## <a name="add-a-key-to-hkeycurrentuser"></a>Добавление раздела в HKEY_CURRENT_USER  
 Следующее дерево синтаксического анализа показан простой сценарий, который добавляет один ключ в системный реестр. В частности, сценарий добавляет ключ `MyVeryOwnKey`в `HKEY_CURRENT_USER`. Он также присваивает строковое значение по умолчанию `HowGoesIt` на новый ключ:  
  
```  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
 Этот сценарий можно легко расширить, добавив задайте несколько подразделов следующим образом:  
  
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
  
 Теперь сценарий добавляет подраздел, `HasASubkey`в `MyVeryOwnKey`. В этом подразделе, и он добавляет `PrettyCool` подраздел (значение по умолчанию `DWORD` значение 55) и `ANameValue` с именем value (со значением строки `WithANamedValue`).  
  
##  <a name="_atl_register_the_registrar_com_server"></a>Зарегистрируйте сервер COM регистратора  
 Следующий скрипт регистрирует сам сервер COM регистратора.  
  
```  
HKCR  
{  
    ATL.Registrar = s 'ATL Registrar Class'  
 {  
    CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
 }  
    NoRemove CLSID  
 {  
    ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = 
    s 'ATL Registrar Class'  
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
  
 Во время выполнения, это дерево синтаксического анализа добавляет `ATL.Registrar` ключа для `HKEY_CLASSES_ROOT`. Этот новый ключ затем ИТ:  
  
-   Указывает `ATL Registrar Class` как строковое значение ключа по умолчанию.  
  
-   Добавляет `CLSID` виде подраздела.  
  
-   Указывает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` для `CLSID`. (Это значение является регистратора CLSID для использования с `CoCreateInstance`.)  
  
 Поскольку `CLSID` является общим, его не следует удалять в режиме отменить регистрацию. Инструкции, `NoRemove CLSID`, делает это, означает, что `CLSID` должен быть открыт в режиме регистр и учитывается в режиме Unregister.  
  
 `ForceRemove` Инструкция предоставляет вспомогательные функции, удалив ключ и все его подразделы перед повторным созданием ключ. Это может быть полезно, если изменились имена подразделов. В этом примере сценария `ForceRemove` проверяет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` уже существует. В этом случае `ForceRemove`:  
  
-   Рекурсивно удаляет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` и все его подразделы.  
  
-   Повторно создает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   Добавляет `ATL Registrar Class` как строковое значение по умолчанию для `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 Дерево синтаксического анализа теперь добавляет два новых разделов в `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. Первый ключ `ProgID`, возвращает строковое значение по умолчанию, — это идентификатор ProgID. Второй ключ `InprocServer32`, возвращает строковое значение по умолчанию, `%MODULE%`, в котором препроцессора значение описано в разделе [с помощью подстановочные параметры (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), данной статьи. `InprocServer32`также возвращает именованное значение `ThreadingModel`, со значением строки `Apartment`.  
  
## <a name="specify-multiple-parse-trees"></a>Укажите несколько синтаксический анализ деревьев  
 Чтобы указать более одного дерево синтаксического анализа в скрипте, просто поместите в конце другого одно дерево. Например, следующий сценарий добавляет ключ `MyVeryOwnKey`, в деревья синтаксического анализа для обоих `HKEY_CLASSES_ROOT` и `HKEY_CURRENT_USER`:  
  
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
>  В скрипте регистратора 4 КБ — максимальный размер маркера. (Маркер представляет любой элемент, распознаваемые в синтаксисе). В предыдущем примере сценария `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, и `'HowGoesIt'` все маркеры.  
  
## <a name="see-also"></a>См. также  
 [Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

