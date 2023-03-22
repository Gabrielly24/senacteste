#  <?php 
    require_once (" ../../conexao/conexao.php ");
    
    // passo 3
    $ consulta_produtos   = " SELECT nomeproduto, preconitario, tempoentrega ";
    $ consulta_produtos .= " FROM produtos ";
    $ consulta_produtos .= " WHERE tempoentrega = 5 ";
    $ produtos = mysqli_query( $ conecta , $ consulta_produtos );

    if ( ! $ produtos ) {
        die(" Falha na consulta ao banco de dados ");
    }

?>
<!doctype html >
<html> _ _
    < cabeça >
        < meta  charset =" UTF-8 " >
        < title > Curso PHP Integração com MySQL </ title >
    </ cabeça >

    < corpo >
        <ol> _ _
        <?php
            while ( $ registro = mysqli_fetch_assoc( $ produtos )) {
        ?>
                <li> < ? php echo $ registro [" nomeproduto " ] ?   > </li>  
    
        <?php    
            }
        ?>
        </ ol >

        <?php
            mysqli_free_result( $ produtos );
        ?>

    </ corpo >
</html> _ _
<?php
    mysqli_close( $ conecta );
?>
