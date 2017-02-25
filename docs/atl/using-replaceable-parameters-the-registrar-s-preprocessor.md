---
title: "Using Replaceable Parameters (The Registrar&#39;s Preprocessor) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddReplacement"
  - "ClearReplacements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%MODULE%"
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using Replaceable Parameters (The Registrar&#39;s Preprocessor)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Подстановочные параметры, позволяющие клиенту регистратора, чтобы определить данные времени выполнения.  Для этого выберите регистратор поддерживает сопоставление замены, в котором он вставляет значения, связанные с параметрами меняемыми в создаваемом скрипте.  Регистратор выполняет эти записи во время выполнения.  
  
##  <a name="_atl_using_.25.module.25"></a> Использование %MODULE%  
 [Мастер элементов управления библиотеки ATL](../atl/reference/atl-control-wizard.md) автоматически формирует скрипт, который использует `%MODULE%`.  Библиотеки ATL используется этот параметр меняемый для фактического расположение библиотеки DLL или EXE сервера.  
  
## Сцепить данные времени выполнения с данными скрипта  
 Другая использование препроцессора сцепления данные времени выполнения с данными скрипта.  Например, предположим, что запись необходима, содержащее полный путь к модулю `, 1`" со строкой ", добавляемым в конце.  Во\-первых, укажите следующее расширение:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Затем, прежде чем вызывать один из методов, перечисленных в [Вызов скрипты](../atl/invoking-scripts.md) обработки сценария добавьте замена в сопоставление:  
  
 [!CODE [NVC_ATL_Utilities#113](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#113)]  
  
 При синтаксическом анализе скрипта, регистратор разверните `'%MODULE%, 1'` к `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  В скрипте регистратора, 4K максимальный размер токена.  Токен любой элемент \(a узнаваемый в синтаксисе\). Это включает в себя токены, которые были созданы или были развернуты препроцессором.  
  
> [!NOTE]
>  Чтобы заменить значения замены во время выполнения, удалите вызов в скрипте к макросу [DECLARE\_REGISTRY\_RESOURCE](../Topic/DECLARE_REGISTRY_RESOURCE.md) или [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md).  Вместо этого замените его собственным методом `UpdateRegistry`, который вызывает [CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md) или [CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md) и передайте этот массив структур **\_ATL\_REGMAP\_ENTRY**.  Этот массив **\_ATL\_REGMAP\_ENTRY** должен иметь по крайней мере одну запись, которая устанавливает в **NULL**} {**NULL**, и эта запись всегда должна быть последней записью.  В противном случае будет сформирована ошибка Нарушения доступа при **UpdateRegistryFromResource** будет вызываются.  
  
> [!NOTE]
>  При построении проекта, выводящий исполняемый файл библиотеки ATL автоматически добавляют кавычки вокруг имени пути создать во время выполнения с параметром скрипта **%MODULE%** регистратора.  Если не требуется, чтобы имя пути включить кавычки, используйте новый параметр **%MODULE\_RAW%**.  
>   
>  При построении проекта, выводящий библиотеки DLL библиотеки ATL не добавляют к имени пути в кавычки, если **%MODULE%** или **%MODULE\_RAW%** используются.  
  
## См. также  
 [Creating Registrar Scripts](../Topic/Creating%20Registrar%20Scripts.md)