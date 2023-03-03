# Hw06
import os
import shutil

EXTENSION_FUNCTIONS = {
    ('JPEG', 'PNG', 'JPG', 'SVG'): 'images',
    ('AVI', 'MP4', 'MOV', 'MKV'): 'video',
    ('DOC', 'DOCX', 'TXT', 'PDF', 'XLSX', 'PPTX'): 'documents',
    ('MP3', 'OGG', 'WAV', 'AMR'): 'audio',
    ('ZIP', 'GZ', 'TAR'): 'archives'
}
known_extensions = set()
unknown_extensions = set()

def normalize(name):
    normalized = ''
    translit_dict = {
        'а': 'a', 'б': 'b', 'в': 'v', 'г': 'g', 'д': 'd',
        'е': 'e', 'ё': 'e', 'ж': 'zh', 'з': 'z', 'и': 'i',
        'й': 'y', 'к': 'k', 'л': 'l', 'м': 'm', 'н': 'n',
        'о': 'o', 'п': 'p', 'р': 'r', 'с': 's', 'т': 't',
        'у': 'u', 'ф': 'f', 'х': 'h', 'ц': 'c', 'ч': 'ch',
        'ш': 'sh', 'щ': 'shch', 'ъ': '', 'ы': 'y', 'ь': '',
        'э': 'e', 'ю': 'yu', 'я': 'ya',
        'А': 'A', 'Б': 'B', 'В': 'V', 'Г': 'G', 'Д': 'D',
        'Е': 'E', 'Ё': 'E', 'Ж': 'Zh', 'З': 'Z', 'И': 'I',
        'Й': 'Y', 'К': 'K', 'Л': 'L', 'М
}
