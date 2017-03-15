---
title: "GetCodeForDllGetClassObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllGetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllGetClassObject - метод"
ms.assetid: 67b61b3b-9784-494f-ba01-17bffa9941ff
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForDllGetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает код для объекта класса DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      function GetCodeForDllGetClassObject(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `nLineStart`  
 Номер строки (с нуля) начала функции.  
  
 `nLineEnd`  
 Отсчитываемый от нуля номер конца функции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая код для получения объекта класса.  
  
## <a name="remarks"></a>Примечания  
 Вызов этой функции-члена для извлечения кода объекта класса. При вызове этой функции создает одну строку путем сцепления заданных элементов массива.  
  
 Ниже приведен код для извлечения кода объекта класса:  
  
|Номер строки|Код|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|Если (S_OK == _AtlModule.GetClassObject (rclsid riid, ppv))|  
|2|\treturn S_OK;|  
|3|Возвращает AfxDllGetClassObject (rclsid, riid, ppv);|  
  
 Для каждой из строк, которые возвращаются `GetCodeForDllGetClassObject` добавляет начальный символ табуляции (`\t`) и конечные пары символов «CR-LF» (возврат каретки и перевод строки) (`\r\n`).  
  
## <a name="example"></a>Пример  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllGetClassObject(1, 2)  
  
// returns the following string  
// "\tif (S_OK == _AtlModule.GetClassObject(rclsid, riid, ppv))\r\n\t\treturn S_OK;\r\n"  
  
```  
  
## <a name="see-also"></a>См. также раздел  
 [Настройка мастеров с ++ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)