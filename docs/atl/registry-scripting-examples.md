---
title: "Registry Scripting Examples | Microsoft Docs"
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
  - "registrar scripts [ATL]"
  - "реестр, Registrar"
  - "сценарии, примеры"
  - "скрипты, Registrar scripts"
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Scripting Examples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создание сценариев в примерах этого раздела показано, как добавлять ключ в системный реестр, зарегистрировать сервер модели COM регистратора и указать несколько деревьев parse.  
  
## Добавьте ключ к HKEY\_CURRENT\_USER  
 Следующие анализируют дерево иллюстрируют простой скрипт, который добавляет один ключ в системный реестр.  В частности, скрипт добавляет ключ, `MyVeryOwnKey`, в `HKEY_CURRENT_USER`.  Кроме того, по умолчанию будет присвоено строковое значение `HowGoesIt?` к новому ключу.  
  
```  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
 Этот скрипт можно легко расширить, чтобы определить несколько подразделов:  
  
```  
HKCU  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
   {  
      'HasASubkey'  
      {  
         'PrettyCool?' = d '55'  
         val 'ANameValue' = s 'WithANamedValue'  
      }  
   }  
}  
```  
  
 Теперь скрипт добавляет подраздел `HasASubkey`, в `MyVeryOwnKey`.  К этому подразделу, он добавляет и подраздел `PrettyCool?` \(значение по умолчанию `DWORD` 55\) и `ANameValue` именованное значение \(со строковым значением `WithANamedValue`\).  
  
##  <a name="_atl_register_the_registrar_com_server"></a> Зарегистрировать сервер модели COM регистратора  
 Следующий скрипт регистрирует сам сервер модели COM регистратора.  
  
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
  
 Во время выполнения этом дерево синтаксического анализа добавляет ключ `ATL.Registrar` к `HKEY_CLASSES_ROOT`.  К этому новому ключу, затем.  
  
-   Определяет `ATL Registrar Class` как строковое значение ключа по умолчанию.  
  
-   Добавляет `CLSID` например подраздела.  
  
-   Определяет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` для `CLSID`.  \(Это значение CLSID регистратора для использования с `CoCreateInstance`\).  
  
 Поскольку `CLSID` совместно использовано, он не должен быть удалено в режиме регистрация которого отменяется.  Оператор, `NoRemove CLSID`, делает это, указав, что `CLSID` должно быть открывается в режиме регистра и игнорирован в режиме регистрация которого отменяется.  
  
 Оператор `ForceRemove` предоставляет функцию домоустройства путем удаления ключ и все его подразделов до повторного создания ключа.  Это может быть полезно, если изменились имена подразделов.  В этом сценарии примере `ForceRemove` проверяет наличие `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` уже существует.  Если это так, `ForceRemove`:  
  
-   Рекурсивно удаляет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` и все его подразделов.  
  
-   Воссоздает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   Добавляет `ATL Registrar Class` как по умолчанию строковое значение для `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 Дерево синтаксического разбора теперь добавляет 2 новых подраздела к `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  Первый ключ, `ProgID` возвращает строковое значение по умолчанию, ProgID.  Второй ключ, `InprocServer32` возвращает строковое значение, `%MODULE%`, которое является значением препроцессора объясненное в разделе [Использование подстановочных параметров \(препроцессор регистратора\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), этой статьи.  `InprocServer32` также возвращает именованное значение, `ThreadingModel` со строковым значением `Apartment`.  
  
## Определите несколько синтаксический анализ деревья  
 Чтобы указать более дерево синтаксического анализа в скрипте, просто устанавливает одно дерево в конце других.  Например, следующий скрипт добавляет ключ, `MyVeryOwnKey`, к деревьям проанализировать, как для `HKEY_CLASSES_ROOT`, так и для `HKEY_CURRENT_USER`:  
  
```  
HKCR  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
> [!NOTE]
>  В скрипте регистратора, 4K максимальный размер токена.  Токен любой элемент \(a узнаваемый в синтаксисе\). В предыдущем сценарии примере `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'` и `'HowGoesIt?'` все токены.  
  
## См. также  
 [Creating Registrar Scripts](../Topic/Creating%20Registrar%20Scripts.md)