---
title: "Возвращаемое программой cl.exe значение | Microsoft Docs"
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
  - "cl.exe - компилятор, возвращаемое значение"
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Возвращаемое программой cl.exe значение
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Программа cl.exe возвращает нулевое значение в случае успешного выполнения \(отсутствия ошибок\) и ненулевое значение во всех остальных случаях.  
  
 Возвращаемое программой cl.exe значение может использоваться при компиляции из файла скрипта, файла powershell, CMD\-файла или BAT\-файла.  Рекомендуется перехватывать выходные данные компилятора, чтобы при необходимости использовать их для устранения возникающих ошибок или предупреждений.  
  
 В программе cl.exe предусмотрено слишком много возможных кодов ошибок завершения cl.exe, чтобы можно было их все перечислить.  Код ошибки можно проверить в файлах winerror.h и ntstatus.h, входящих в пакет средств разработки программного обеспечения для Windows в каталоге %ProgramFiles\(x86\)%\\Windows Kits\\`version`\\Include\\shared\\.  Коды ошибок, возвращенные в виде десятичного числа, для поиска необходимо преобразовать в шестнадцатеричный вид.  Например, код ошибки \-1073741620 преобразуется в шестнадцатеричный код 0xC00000CC.  Эта ошибка находится в файле ntstatus.h, в котором приведено соответствующее сообщение "Общий ресурс с указанным именем не найден на удаленном сервере". Загружаемый список кодов ошибок Windows см. в разделе [&#91;MS\-ERREF&#93;: Windows Error Codes](http://msdn.microsoft.com/ru-ru/1bc92ddf-b79e-413c-bbaa-99a5281a6c90).  
  
 Для выяснения значения ошибки компилятора можно также использовать программу поиска ошибок в Visual Studio.  В командной оболочке Visual Studio введите **errlook.exe**, чтобы запустить программу; можно также в интегрированной среде разработки Visual Studio выбрать в строке меню пункты **Сервис**, **Поиск ошибки**.  Введите значение ошибки, чтобы найти связанный с ней описательный текст.  Дополнительные сведения см. в разделе [Справочник ERRLOOK](../../build/reference/errlook-reference.md).  
  
## Заметки  
 Ниже приведен пример BAT\-файла, в котором используется значение, возвращаемое программой cl.exe.  
  
```  
echo off  
cl /W4 t.cpp  
@if ERRORLEVEL == 0 (  
   goto good  
)  
  
@if ERRORLEVEL != 0 (  
   goto bad  
)  
  
:good  
   echo "clean compile"  
   echo %ERRORLEVEL%  
   goto end  
  
:bad  
   echo "error or warning"  
   echo %ERRORLEVEL%  
   goto end  
  
:end  
```  
  
## См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)