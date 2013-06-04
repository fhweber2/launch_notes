Finding the Mean, Median, Mode

    def mean (array)
        array.inject(0) {|sum x| sum += x } / array.size.to_f
    end



Standard Deviation

    def mean_st_dev (array)
        m = mean(array)
        variance = array.inject(0) { |variance, x| variance =+ (x - m) ** 2 }
        return m, Math.sqrt(variance/array.size-1)
    end
    



    
