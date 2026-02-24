import os
import shutil

def organize_folder(path):
    files = [f for f in os.listdir(path) if os.path.isfile(os.path.join(path, f))]
    for file in files:
        ext = file.split('.')[-1]
        if not os.path.exists(os.path.join(path, ext)):
            os.makedirs(os.path.join(path, ext))
        shutil.move(os.path.join(path, file), os.path.join(path, ext, file))
    print("Files organized by extension.")

if __name__ == "__main__":
    print("Organizer ready to scan...")
