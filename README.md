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

for filename in os.listdir():
    _, extension = os.path.splitext(filename)
    extension = extension.lstrip('.')
        
    for extensions, category in EXTENSION_FUNCTIONS.items():
        if extension.upper() in extensions:
            shutil.move(filename, category)
            break
