---
title: importidl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd930ef70e5bb2b87c584c1d821cdf4528580a31
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607187"
---
# <a name="importidl"></a>importidl
Вставляет указанный IDL-файла в созданного IDL-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ importidl(  
   idl_file  
) ];  
```  
  
### <a name="parameters"></a>Параметры  
 *idl_file*  
 Определяет имя IDL-файла, которые необходимо объединить с IDL-файла, создаваемого для вашего приложения.  
  
## <a name="remarks"></a>Примечания  
 **Importidl** атрибут C++ помещает разделе за пределами блока библиотеки (в *idl_file*) в вашей программе созданного IDL-файла и в разделе библиотеки (в *idl_file*) в библиотеку раздел для вашей программы создается IDL-файла.  
  
 Вы можете использовать **importidl**, например, если вы хотите использовать с вашей созданного IDL-файла вручную IDL-файл.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [Импорт](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [включить](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   