---
title: "Страницы свойств HLSL: Выходные файлы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04f6ad8889c9a713b3b64284b329c21d5a2cd49e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hlsl-property-pages-output-files"></a>Страницы свойств HLSL. Выходные файлы
Чтобы настроить следующие свойства компилятор HLSL (fxc.exe), используйте его **выходные файлы** свойство. Сведения о доступе к **выходные файлы** см. на странице свойств в папке HLSL [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Имя переменной заголовок**  
 Указывает имя массива, используемый для кодировке объектного кода HLSL. Массив содержится в файле заголовка, который выдается компилятором HLSL. Имя файла заголовка определяется **имя файла заголовка** свойство.  
  
 Это свойство соответствует **/Vn [name]** аргумент командной строки.  
  
 **Имя файла заголовка**  
 Задает имя файла заголовка, который выдается компилятором HLSL. Заголовок содержит объектного кода HLSL, кодируются в массив. Имя массива определяется **имя переменной заголовок** свойство.  
  
 Это свойство соответствует **/Fh [name]** аргумент командной строки.  
  
 **Имя объектного файла**  
 Задает имя объектного файла, который выдается компилятором HLSL. Значением по умолчанию является **.cso % (имя файла) $(OutDir)**.  
  
 Это свойство соответствует **/Fo [name]** аргумент командной строки.  
  
 **Ассемблер выходной**  
 **Список сборок (/ Fc)** для вывода только инструкций на языке ассемблера. **Код сборки и шестнадцатеричный код (/ Fx)** для вывода инструкций на языке ассемблера и соответствующий код операции в шестнадцатеричном формате. По умолчанию выводится отсутствует в списке.  
  
 **Ассемблер выходной файл**  
 Задает имя файла списка сборок, который выдается компилятором HLSL.  
  
 Это свойство соответствует **/Fc [name]** и **/Fx [name]** аргументы командной строки.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств HLSL](../ide/hlsl-property-pages.md)   
 [Страницы свойств HLSL: Общие](../ide/hlsl-property-pages-general.md)   
 [Страницы свойств HLSL: "Дополнительно"](../ide/hlsl-property-pages-advanced.md)