# 📋 Sobre o projeto
### O projeto dos `snippets` foi criado com o objetivo de ajudar a todos os devs em php que utilizam do framework <b>Laminas</b>.. o antigo <b>Zend</b>, mas claro que ele não serve apenas para essa galera, o projeto tambem se adequa aqueles que buscam mais agilidade na hora de debugar e escrever seus códigos.

## ✅ Os snippets que a extenção atual possui são:


### 📌 Select completo com o laminas
- sqlc 
``` 
$sql    = new Sql($this->$var);
$select = $sql->select();
$where  = new Where();

// $where;

$select->from(['t'=>'table'])
->where($where);

$rows = [];

$rs = $sql->prepareStatementForSqlObject($select)->execute();

foreach($rs as $ln)
{
    $bar[] = $ln;
}

return $rows;
```
### 📌 Select de apenas um campo com o laminas
- sqlm
``` 
$sql    = new Sql($this->$var);
$select = $sql->select();
$where  = new Where();

// $where;

$select->from(['t'=>'table'])
->where($where);

return $sql->prepareStatementForSqlObject($select)->execute()->current();
```

### 📌 Update simples com o laminas
- sqlu
``` 
$sql   = new Sql($this->variable);
$where = new Where();

$where->equalTo('value','value');

$update = $sql->update('table')
->set([
    'column' => 'value'
])
->where($where);

$sql->prepareStatementForSqlObject($update)->execute();
```

### 📌 Retorna a string do select com o laminas

- sqlbs `echo $this->var->buildSqlString($select); die();`

## 📌 Outros

- php  `<?php  ?>`
- ephp `<?=    ?>`
- cphp `?>     <?php`
- issem  `(isset($v) && !empty($v) ? true : false)`
- dd     `echo '<pre>'; var_dump($v) die(); `
- decode `mb_convert_encoding($v, 'UTF-8', 'ISO-8859-1')`
