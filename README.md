# lab-01-insercao-lista-duplamente-encadeada-leomatos01
lab-01-insercao-lista-duplamente-encadeada-leomatos01 created by GitHub Classroom
class Node:

    def _init_(self, x):
        self.x = x
        self.next = None
        self.prev = None


class Lista:

    def _init_(self):
        self.init = None
        self.tail = None

    def append(self, node):
        """
        Método para inserir um elemento no final
        :param node:
        :return:
        """
        if self.init is None:
            self.init = node
            self.tail = node
            return

        
    
        self.tail.next = node
        node.prev = self.tail
        """
        --
        """
        self.tail = node

    def add(self, node):
        """
        Inserir um elemento sempre no inicio da lista
        :param node:
        :return:
        """
        if self.init is None:
            self.init = node
            self.tail = node
            return

        node.next = self.init
        self.init = node

        
        

    def _str_(self):
        str_aux = '['
        node_aux = self.init
        while(node_aux is not None):
            str_aux += str(node_aux.x) + ','
            node_aux = node_aux.next
        str_aux += ']'
        return str_aux


    
if _name_ == '_main_':
    lista = Lista()
    lista.add(Node(x=27))
    lista.add(Node(x=1))
    print(lista)
    lista.append(Node(x=5))
    lista.append(Node(x=19))
    lista.append(Node(x=5555))
    print(lista)
