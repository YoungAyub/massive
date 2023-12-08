


Задача 1: Получение значения элемента из двумерного массива

def get_element(matrix, row, col):
    try:
        value = matrix[row][col]
        return f"Значение элемента на позиции ({row}, {col}): {value}"
    except IndexError:
        return "Указанной позиции не существует в массиве."

# Пример использования
matrix_example = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

position_row = int(input("Введите номер строки: "))
position_col = int(input("Введите номер столбца: "))

result = get_element(matrix_example, position_row, position_col)
print(result)
Задача 2: Обмен первой и последней строки массива

def swap_first_last_row(matrix):
    matrix[0], matrix[-1] = matrix[-1], matrix[0]

# Пример использования
matrix_example = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

swap_first_last_row(matrix_example)

# Вывод измененного массива
for row in matrix_example:
    print(row)
Задача 3: Поиск строки с наименьшей суммой элементов

def find_min_sum_row(matrix):
    min_sum = float('inf')
    min_sum_row = None

    for i, row in enumerate(matrix):
        current_sum = sum(row)
        if current_sum < min_sum:
            min_sum = current_sum
            min_sum_row = i

    return f"Строка с наименьшей суммой элементов: {min_sum_row}"

# Пример использования
matrix_example = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

result = find_min_sum_row(matrix_example)
print(result)
Задача 4*: Удаление строки и столбца с наименьшим элементом

def remove_row_and_col_with_min_element(matrix):
    min_element = float('inf')
    min_row, min_col = None, None

    # Находим наименьший элемент и его позицию
    for i, row in enumerate(matrix):
        for j, element in enumerate(row):
            if element < min_element:
                min_element = element
                min_row, min_col = i, j

    # Удаляем строку и столбец с наименьшим элементом
    new_matrix = [
        row[:min_col] + row[min_col + 1:] for k, row in enumerate(matrix) if k != min_row
    ]

    return new_matrix

# Пример использования
matrix_example = [
    [3, 1, 2],
    [4, 5, 6],
    [7, 8, 9]
]

result_matrix = remove_row_and_col_with_min_element(matrix_example)

# Вывод измененного массива
for row in result_matrix:
    print(row)






