---
title: "Обработка ошибок в файлах JScript мастеров | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка ошибок, JScript"
  - "JScript, обработка ошибок"
  - "Wizard JScript - обработчик ошибок"
ms.assetid: 6df3ba46-7ab6-484c-ac45-b08f4b6a5900
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Обработка ошибок в файлах JScript мастеров
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании мастера проект включает файлы Default.js и Сommon.js.  Эти файлы используются для настройки проекта.  Дополнительные сведения см. в разделе [Файл JScript](../ide/jscript-file.md).  
  
 Проект должен включать обработку ошибок.  Далее приводится пример такого кода.  
  
### Обработка ошибок в файле JScript  
  
1.  Для перехвата ошибок при щелчке пользователем по кнопке **Готово** введите следующий код:.  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       try  
       {  
          .....  
       }  
       catch(e)  
       {  
          if (e.description.length != 0)  
             SetErrorInfo(e.description, e.number);  
          return e.number  
       }  
    }  
    ```  
  
2.  Вызовите исключение `e` из любых вспомогательных функций скрипта, вызываемых в сценарии:  
  
    ```  
    function ExtenderFromType(strVariableType)  
    {  
       try  
       {  
          ....  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
3.  Если параметр **PREPROCESS\_FUNCTION** находится в [VSZ\-файле](../ide/dot-vsz-file-project-control.md), мастер вызовет функцию [CanAddATLClass](../ide/jscript-functions-for-cpp-wizards.md).  В случае ошибки необходимо использовать функцию [Функция SetErrorInfo](../ide/seterrorinfo.md), и должно быть возвращено значение **false**:  
  
    ```  
    function CanAddATLClass(oProj, oObject)  
    {  
       try  
       {  
          if (!IsATLProject(oProj))  
          {  
             if (!IsMFCProject(oProj, true))  
             {     
                var L_CanAddATLClass_Text = "ATL classes can only be added  
     to ATL, MFC EXE and MFC regular DLL projects.";  
                wizard.ReportError(L_CanAddATLClass_Text);  
                return false;  
             }  
             else  
             {  
                .....  
                var bRet = AddATLSupportToProject(oProj);  
                .....  
                return bRet;  
             }  
          }  
          return true;  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
4.  Если необходимо вернуться в диалоговое окно **Новый проект** или **Добавление нового элемента**, должно быть возвращено **VS\_E\_WIZBACKBUTTONPRESS**:  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       ....  
       if (!CheckAddtoProject(selProj))  
       {  
          return VS_E_WIZARDBACKBUTTONPRESS;  
       }  
    }  
    ```  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Настройка мастера](../ide/customizing-your-wizard.md)