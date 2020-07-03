# Format Phonenumber Indonesia Laravel
    function format_phone_idn($numb) {
        if (!is_numeric(substr($numb, 0, 1))  && !is_numeric(substr($numb, 1, 1))) 
        {
           return $numb; 
        }

        $chars = array(' ', '(', ')', '-', '.');
        $numb = str_replace($chars, "", $numb);

        if (strlen($numb) > 10) {
          $numb = sprintf('+62', 1, 4) . '-' .
                  substr($numb, 1, 3) . '-' .
                  substr($numb, 4, 4) . '-' .
                  substr($numb, 8, 4);
                  // return : +62-896-8222-1200
        }
        else {
          $numb = sprintf('+62', 1, 4) . '-' .
                  substr($numb, 1, 3) . '-' .
                  substr($numb, 4, 4) . '-' .
                  substr($numb, 8, 4);
                  // return : +62-896-8222-12
        }

        return $numb;
    }
