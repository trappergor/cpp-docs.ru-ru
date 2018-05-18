---
title: Импорт | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b371cd1094a49f8a629cb6f8e880fd1210670f91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="import"></a>импорт
Указывает другой файл IDL, .odl или заголовок, содержащий определения, которые нужно сделать ссылку из вашего основного языка IDL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 `idl_file`  
 Имя IDL-файла, который необходимо импортировать в библиотеку типов текущего проекта.  
  
## <a name="remarks"></a>Примечания  
 **Импорта** языка C++ вызывает `#import` инструкцию, чтобы поместить под `import "docobj.idl"` инструкции в сгенерированный IDL-файл. **Импорта** атрибут имеет ту же функциональность, что [импорта](http://msdn.microsoft.com/library/windows/desktop/aa367047) языка MIDL.  
  
 **Импорта** атрибут только помещает указанный файл в IDL-файла, создаваемого проектом; **импорта** атрибут позволяет вызывать конструкции в указанный файл из исходного кода в проекте.  Чтобы вызвать конструкции в указанный файл из исходного кода в проекте, либо использовать [#import](../preprocessor/hash-import-directive-cpp.md) и `embedded_idl` атрибута или включить h-файл для `idl_file`, если существует h-файл.  
  
## <a name="example"></a>Пример  
 В приведенном ниже коде  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 Создает следующий код в сгенерированный IDL-файл:  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [Включить](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
