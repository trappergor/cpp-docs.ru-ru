---
title: "CanUseFileName | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanUseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanUseFileName - метод"
ms.assetid: 60b669fa-9484-4435-b502-78ec8e960a00
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanUseFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, существует ли файл.  Если файл существует и доступ к нему не ограничен, мастер предлагает пользователю объединить код, который должен быть добавлен в существующий файл.  
  
## Синтаксис  
  
```  
  
      function CanUseFileName(   
   strFileName,   
   bCheckIfMidlHeader,   
   bCannotExist,   
   bSetMergeFlag    
);  
```  
  
#### Параметры  
 `strFileName`  
 Имя файла для проверки.  
  
 *bCheckIfMidlHeader*  
 Установите значение на **true**, чтобы проверить, было ли имя файла создано с помощью MIDL.  
  
 *bCannotExist*  
 Установите значение на **true**, чтобы проверить, что данное имя файла уже существует и не может быть перезаписано.  
  
 *bSetMergeFlag*  
 Установите значение на **true**, чтобы включить символ MERG\_FILE, который указывает на возможность добавления кода в существующий файл.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если `strFileName` является уникальным или если код может быть добавлен в существующий файл; в противном случае возвращает значение **false**.  
  
## Заметки  
 Эта функция вызывается для проверки существования данного имени файла.  Если файл существует и не был создан с помощью MIDL, или доступ к нему не ограничен иным образом, данная функция предлагает пользователю добавить новый код в существующий файл.  
  
 Если файла с указанным именем не существует и оно не является ограниченным, создается файл с указанным именем.  
  
 Если имя файлы было создано с помощью MIDL или доступ к нему ограничен иным образом, мастер выводит сообщение об ошибке.  
  
## Пример  
  
```  
case "HTML_FILE":  
if (!HTML_FILE.disabled)  
   {  
   if (!window.external.FindSymbol("HTML_FILE_VALID"))  
      {  
      bValid = CanUseFileName(obj.value, false, true);  
      if (!bValid)  
      break;  
      window.external.AddSymbol("HTML_FILE_VALID", true)  
      }  
   }  
   bValid = window.external.ValidateFile(HTML_FILE.value, vsCMValidateFileExtHtml);  
   break;   
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)